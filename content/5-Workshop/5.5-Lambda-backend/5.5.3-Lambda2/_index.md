---
title: "Websocket API Handler"
date: 2026-07-27
weight: 5
chapter: false
pre: " <b> 5.5.3 </b> "
---

#### 5.5.3. Lambda 2: WebSocket API Handler (RealtimeChatHandler)

This function acts as the real-time routing engine. It manages WebSocket connections, saves incoming messages to DynamoDB, and broadcasts them to active users.

1. Create a second function named **`RealtimeChatHandler`** using **Python 3.12** and the same **`ChatApp_Lambda_Role`**.


2. Paste the following code and click Deploy:

```python
import json
import boto3
import time
import uuid

dynamodb = boto3.client('dynamodb')
CONNECTIONS_TABLE = 'Connections'
MESSAGES_TABLE = 'Messages'
ROOMS_TABLE = 'Rooms'

def lambda_handler(event, context):
    route_key = event.get('requestContext', {}).get('routeKey')
    connection_id = event.get('requestContext', {}).get('connectionId')
    domain_name = event.get('requestContext', {}).get('domainName')
    stage = event.get('requestContext', {}).get('stage')

    if route_key == '$connect':
        username = event.get('queryStringParameters', {}).get('username', 'Unknown')
        dynamodb.put_item(TableName=CONNECTIONS_TABLE, Item={'connectionID': {'S': connection_id}, 'username': {'S': username}})
        return {'statusCode': 200, 'body': 'Connected'}

    elif route_key == '$disconnect':
        dynamodb.delete_item(TableName=CONNECTIONS_TABLE, Key={'connectionID': {'S': connection_id}})
        return {'statusCode': 200, 'body': 'Disconnected'}

    elif route_key == 'sendMessage':
        body = json.loads(event.get('body', '{}'))
        action_type = body.get('type') 
        
        apigw_management = boto3.client('apigatewaymanagementapi', endpoint_url=f"https://{domain_name}/{stage}")

        if action_type == 'createRoom':
            room_name = body.get('roomName')
            members = body.get('members', '')
            new_room_id = str(uuid.uuid4())[:8] 
            dynamodb.put_item(TableName=ROOMS_TABLE, Item={'roomID': {'S': new_room_id},'roomName': {'S': room_name},'members': {'S': members}})
            msg_to_send = json.dumps({'type': 'system', 'text': f'Đã tạo phòng {room_name}'})
            apigw_management.post_to_connection(ConnectionId=connection_id, Data=msg_to_send.encode('utf-8'))
            return {'statusCode': 200, 'body': 'Room created'}

        elif action_type == 'chat':
            sender = body.get('sender')
            text = body.get('text')
            room_id = body.get('roomID', 'global')
            is_image = body.get('isImage', False) 
            
            timestamp = str(int(time.time() * 1000))
            
            dynamodb.put_item(
                TableName=MESSAGES_TABLE,
                Item={
                    'roomID': {'S': room_id}, 
                    'timestamp': {'N': timestamp}, 
                    'sender': {'S': sender}, 
                    'text': {'S': text},
                    'isImage': {'BOOL': is_image} 
                }
            )
            
            target_members = []
            is_public = False
            
            if room_id != 'global':
                room_data = dynamodb.get_item(TableName=ROOMS_TABLE, Key={'roomID': {'S': room_id}})
                if 'Item' in room_data:
                    members_str = room_data['Item'].get('members', {}).get('S', '')
                    if not members_str: is_public = True
                    else: target_members = [m.strip() for m in members_str.split(',')]

            response = dynamodb.scan(TableName=CONNECTIONS_TABLE)
            online_connections = response.get('Items', [])
            
            message_to_send = json.dumps({'type': 'chat', 'roomID': room_id, 'sender': sender, 'text': text, 'timestamp': timestamp, 'isImage': is_image})

            for conn in online_connections:
                c_id = conn['connectionID']['S']
                c_user = conn.get('username', {}).get('S', '')
                if room_id == 'global' or is_public or c_user in target_members:
                    try: apigw_management.post_to_connection(ConnectionId=c_id, Data=message_to_send.encode('utf-8'))
                    except: dynamodb.delete_item(TableName=CONNECTIONS_TABLE, Key={'connectionID': {'S': c_id}})
            return {'statusCode': 200, 'body': 'Sent'}

        elif action_type == 'addMember':
            room_id = body.get('roomID')
            new_members = body.get('newMembers')
            
            room_data = dynamodb.get_item(TableName=ROOMS_TABLE, Key={'roomID': {'S': room_id}})
            if 'Item' in room_data:
                current_members = room_data['Item'].get('members', {}).get('S', '')
                room_name = room_data['Item'].get('roomName', {}).get('S', 'Unknown')
                
                list_current = [m.strip() for m in current_members.split(',') if m.strip()]
                list_new = [m.strip() for m in new_members.split(',') if m.strip()]
                final_members = list(set(list_current + list_new))
                
                dynamodb.update_item(
                    TableName=ROOMS_TABLE,
                    Key={'roomID': {'S': room_id}},
                    UpdateExpression="SET members = :m",
                    ExpressionAttributeValues={':m': {'S': ','.join(final_members)}}
                )
                
                msg = json.dumps({'type': 'system', 'text': f'Đã mời thêm người vào {room_name} thành công!'})
                apigw_management.post_to_connection(ConnectionId=connection_id, Data=msg.encode('utf-8'))
            return {'statusCode': 200, 'body': 'Member added'}

    return {'statusCode': 400, 'body': 'Unknown route'}