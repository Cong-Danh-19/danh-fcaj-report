---
title: "Workshop"
date: 2026-07-27
weight: 5
chapter: false
pre: " <b> 5. </b> "
---
# Building a Serverless Real-time Chat App

#### Overview

**Serverless Architecture** allows you to build and run applications and services without thinking about servers. It eliminates infrastructure management tasks such as server or cluster provisioning, patching, operating system maintenance, and capacity provisioning.

In this lab, you will learn how to build a fully functional, real-time chat application using a **Hybrid API approach** on AWS. We will combine a REST API (for static data fetching) and a WebSocket API (for low-latency real-time bidirectional communication).

You will configure and integrate multiple AWS services:
+ **Amazon Cognito** - For secure user authentication and registration.
+ **Amazon DynamoDB** - To store chat messages, room details, and active connection IDs.
+ **AWS Lambda** - To execute backend logic for both REST and WebSocket APIs.
+ **Amazon API Gateway** - To route traffic from the frontend to our backend functions.
+ **Amazon S3** - To host the React frontend and securely store media files using Presigned URLs.
+ **Amazon CloudFront** - To globally distribute the application with high performance and HTTPS security.

#### Content

1. [Overview](5.1-Overview/)
2. [Prerequisites](5.2-Prerequisites/)
3. [Step 1: Authentication with Cognito](5.3-Cognito-Auth/)
4. [Step 2: Database Setup](5.4-DynamoDB/)
5. [Step 3: Compute & IAM Security](5.5-Lambda-backend/)
6. [Step 4: API Routing](5.6-API-gateway/)
7. [Step 5: Image Storage with S3](5.7-S3-Media-Storage/)
8. [Step 6: Frontend Hosting with S3](5.8-S3-Web-hosting/)
9. [Step 7: Global Delivery with CloudFront](5.9-Cloudfront/)
10. [Clean up](5.10-Cleanup/)