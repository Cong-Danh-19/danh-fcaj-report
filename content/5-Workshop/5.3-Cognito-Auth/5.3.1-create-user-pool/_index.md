---
title : "Create user pool"
date : 2026-07-27 
weight : 3
chapter : false
pre : " <b> 5.3.1 </b> "
---
#### 5.3.1. Create a User Pool

1. Navigate to the **Amazon Cognito** service in the AWS Management Console.
2. Click on **Create user pool**.
![Create Configuration](/images/5-Workshop/5.3-Cognito-auth/Screenshot1.png)
3. In the *Define your application* step, choose **Single-page application (SPA)** since we are using ReactJS.
4. Name your application (e.g., `ChatAppClient`).
5. Under *Options for sign-in identifiers*, select **Email**. This ensures users use their email address as their username.
6. Under *Self-registration*, check the box for **Enable self-registration** so new users can create their own accounts from our frontend.
![Cognito Configuration](/images/5-Workshop/5.3-Cognito-auth/Screenshot2.png)
7. Click on **Create user directory**
![create user dir](/images/5-Workshop/5.3-Cognito-auth/Screenshot3.png)

