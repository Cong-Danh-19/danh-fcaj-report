---
title : "Create the DynamoDB Tables"
date : 2026-07-28
weight : 4
chapter : false
pre : " <b> 5.4.2 </b> "
---

#### 5.4.2. Create the DynamoDB Tables

Navigate to the **DynamoDB** service in the AWS Console and click **Create table**. You need to create **three separate tables** with the exact names and Partition/Sort keys listed below (Case-sensitive):

**1. The `Connections` Table**
* **Table name:** `Connections`
* **Partition key:** `connectionID` (String)
* *Purpose:* Temporarily stores the IDs of users who have an active WebSocket connection. This allows the backend to know who to broadcast messages to.
![DynamoDB Tables](/images/5-Workshop/5.4-DynamoDB/Screenshot2.PNG)

**2. The `Rooms` Table**
* **Table name:** `Rooms`
* **Partition key:** `roomID` (String)
* *Purpose:* Stores details about chat rooms, such as the room name and the list of members (to support private and group chats).
![DynamoDB Tables](/images/5-Workshop/5.4-DynamoDB/Screenshot4.PNG)

**3. The `Messages` Table**
* **Table name:** `Messages`
* **Partition key:** `roomID` (String)
* **Sort key:** `timestamp` (Number)
* *Purpose:* Stores the chat history. The `timestamp` Sort Key is essential here because it allows us to easily query and sort messages chronologically from oldest to newest.

For the capacity settings, you can leave them as **Provisioned** (the default) to stay within the AWS Free Tier.

![DynamoDB Tables](/images/5-Workshop/5.4-DynamoDB/Screenshot5.PNG)
Wait a few moments until the status of all three tables becomes **Active**. Our database layer is now ready!
![DynamoDB Tables](/images/5-Workshop/5.4-DynamoDB/Screenshot6.png)
