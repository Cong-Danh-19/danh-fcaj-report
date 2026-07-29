---
title: "IAM Role Configuration"
date: 2026-07-27
weight: 5
chapter: false
pre: " <b> 5.5.1 </b> "
---

#### 5.5.1. IAM Role Configuration

Before creating the Lambda functions, we must give them the exact permissions they need to interact with other AWS services.

1. Navigate to the **IAM** service in the AWS Console, select **Roles**, and click **Create role**.
![IAM Role Setup](/images/5-Workshop/5.5-Lambda-backend/Screenshot1.png)
2. Choose **AWS service** as the trusted entity and **Lambda** as the use case. Then click on **Next**.
![IAM Role Setup](/images/5-Workshop/5.5-Lambda-backend/Screenshot2.png)
3. Attach the following managed policies:
   * `AmazonDynamoDBFullAccess` *(To read/write chat data)*
   * `AmazonS3FullAccess` *(To generate Presigned URLs for images)*
   * `AmazonCognitoReadOnly` *(To fetch the user list)*
   * `AmazonAPIGatewayInvokeFullAccess` *(To send WebSocket messages back to clients)*
   * `AWSLambdaBasicExecutionRole` *(To write logs to CloudWatch)*
![IAM Role Setup](/images/5-Workshop/5.5-Lambda-backend/Screenshot3.png)
![IAM Role Setup](/images/5-Workshop/5.5-Lambda-backend/Screenshot4.png)
![IAM Role Setup](/images/5-Workshop/5.5-Lambda-backend/Screenshot5.png)
![IAM Role Setup](/images/5-Workshop/5.5-Lambda-backend/Screenshot6.png)
![IAM Role Setup](/images/5-Workshop/5.5-Lambda-backend/Screenshot7.png)
4. Click on **Next**.
5. Name the role **`ChatApp_Lambda_Role`**, review the **Permissions policies** and create it.

![IAM Role Setup](/images/5-Workshop/5.5-Lambda-backend/Screenshot8.png)
![IAM Role Setup](/images/5-Workshop/5.5-Lambda-backend/Screenshot9.png)