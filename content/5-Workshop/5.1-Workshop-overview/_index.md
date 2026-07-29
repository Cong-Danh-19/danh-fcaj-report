---
title: "Overview"
date: 2026-07-27
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

### Introduction
This workshop will guide you step-by-step through the process of building a **Serverless Hybrid Real-time Chat Application** on AWS. 

Instead of relying on traditional, always-on servers (like Amazon EC2), this application adopts a 100% Serverless architecture. This approach ensures high scalability, zero server maintenance, and minimal costs (pay-as-you-go model). Furthermore, the application uses a **Hybrid API design**, separating static data requests from real-time communication to optimize both performance and cost.

### Architecture Diagram

Below is the overall architecture of the system we are going to build:

![Architecture Diagram](/images/WorkshopDiagram.drawio.png)

### How the system works

The system is decoupled into specific data flows:
1. **Hosting & Content Delivery**: The ReactJS frontend is hosted on **Amazon S3** and distributed globally via **Amazon CloudFront** to provide ultra-low latency and HTTPS security.
2. **Authentication**: Users sign up and log in using **Amazon Cognito**. Cognito manages user sessions and securely passes user identifiers to our APIs.
3. **Static Data Flow (REST API)**: When a user opens a chat room, the frontend calls the **Amazon API Gateway (HTTP API)**. This triggers an **AWS Lambda** function to retrieve the chat history and user lists from **Amazon DynamoDB**.
4. **Real-time Data Flow (WebSocket API)**: To enable instant messaging, the frontend establishes a persistent connection with the **Amazon API Gateway (WebSocket API)**. Messages sent by users are processed by a Lambda function and broadcasted immediately to all currently online users in the room.
5. **Media Upload**: Instead of passing heavy image files through Lambda, the system requests a **Presigned URL** from S3. The frontend then uploads the image directly to an S3 bucket, reducing backend workload and saving costs.

In the next sections, we will deploy these components step-by-step. Let's get started!