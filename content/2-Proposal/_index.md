---
title: "Proposal"
date: 2026-07-27
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Serverless Real-time Chat Application on AWS

### 1. Executive Summary
The "Serverless Real-time Chat Application" project is designed to provide an ultra-low latency online communication platform, supporting global, private group, and direct (1-1) chat rooms. The project maximizes the power of AWS Serverless architecture (API Gateway, Lambda, DynamoDB) combined with an approach: using a REST API for static data and a WebSocket API for real-time data streams.

### 2. Problem Statement
**What’s the Problem?**
Traditional REST-based chat applications suffer from high latency due to continuous polling, wasting network resources. Conversely, maintaining dedicated WebSocket servers (like EC2 instances) incurs high fixed monthly costs, is difficult to auto-scale during traffic spikes, and wastes resources during idle times.

**The Solution**
This platform utilizes a 100% Serverless architecture. **Amazon Cognito** manages user authentication. Real-time data is handled via **Amazon API Gateway (WebSocket)** and AWS Lambda, maintaining bi-directional connections without virtual servers. Message history is retrieved via **API Gateway (HTTP API)**. Images and media files are uploaded directly to **Amazon S3** via Presigned URLs, completely offloading the backend. The frontend interface (ReactJS) is hosted on S3 and distributed globally via **Amazon CloudFront**.

**Benefits and Return on Investment**
The solution completely eliminates server maintenance costs (Zero Server Maintenance). Leveraging the AWS Free Tier, monthly operating costs are nearly $0 for research scale. The system features auto-scaling capabilities to serve thousands of concurrent connections seamlessly.

### 3. Solution Architecture
The system uses a Decoupled Architecture. The Frontend communicates with AWS through 2 separate gateways: HTTP API (REST) for heavy/static tasks and WebSocket API for ultra-light message streams.

![Solution Architecture](/images/WorkshopDiagram.drawio.png)

**AWS Services Used:**
- **Amazon S3:** Static frontend hosting (ReactJS) and media storage.
- **Amazon CloudFront:** Content Delivery Network (CDN) for fast loading and HTTPS.
- **Amazon Cognito:** User Pool management and secure authentication.
- **Amazon API Gateway:** Provides both HTTP API (REST) and WebSocket API protocols.
- **AWS Lambda:** Handles backend logic using Python (connection routing, messages, Presigned URLs).
- **Amazon DynamoDB:** NoSQL database storing Rooms, Messages, and active Connections.
- **AWS IAM:** Strict access control following the Principle of Least Privilege.

### 4. Technical Implementation
**Implementation Phases**
- **Phase 1 (Environment & Auth):** Initialize environment, set up IAM, and integrate Amazon Cognito authentication into ReactJS.
- **Phase 2 (Database & REST Backend):** Design DynamoDB tables and build HTTP API for retrieving message history and user lists.
- **Phase 3 (Real-time Engine & Media):** Build WebSocket API for routing messages by room (Private/Public) and configure S3 Presigned URLs for image uploads.
- **Phase 4 (Frontend Integration & Deployment):** Integrate ReactJS UI, perform End-to-End testing, and deploy the website to the Internet via CloudFront.

**Technical Requirements**
- Frontend: ReactJS, interacting via `aws-amplify` and `Fetch API`.
- Backend: AWS Lambda written in Python (boto3 SDK).
- Security: Strict CORS configurations on API Gateway and S3 Bucket Policies.

### 5. Timeline & Milestones
- **Month 1:** Research Serverless architecture, familiarize with Amazon Cognito, and design DynamoDB schemas.
- **Month 2:** Develop Backend (Lambda, API Gateway) and implement WebSocket routing mechanisms.
- **Month 3:** Refine Frontend UI/UX, integrate S3 image upload feature, perform bug testing, and deploy the product on CloudFront. Write final reports.

### 6. Budget Estimation
The entire architecture is optimized to fit within the **AWS Free Tier**. The estimated actual monthly cost is **$0.00**. Below is the estimation if exceeding the Free Tier (Load of 10,000 messages/month):
- AWS Lambda: $0.00 (Free up to 1M requests/month).
- Amazon API Gateway: ~$0.05 (WebSocket connection time).
- Amazon DynamoDB: $0.00 (25 GB storage free).
- Amazon S3 & CloudFront: ~$0.10 (Data transfer out & media storage).
- **Total Estimated Cost:** < $0.5 / month.

### 7. Risk Assessment
**Risk Matrix:**
- Network Drop (WebSocket): High impact, Medium probability.
- CORS Security Errors: High impact, High probability.
- Lambda Payload Exceeded (Large file uploads): Medium impact, Low probability.

**Mitigation Strategies:**
- **Network:** Design the Frontend (React) to auto-reconnect when WebSockets drop.
- **CORS:** Explicitly set Allow-Origins and Allow-Headers on both API Gateway and S3.
- **Large Files:** Use S3 Presigned URLs so the client uploads files directly to S3, only transmitting the text link via WebSocket, offloading Lambda 100%.

### 8. Expected Outcomes
**Technical Improvements:**
A serverless messaging platform that saves resources when idle. Ultra-low latency for real-time messaging. A clear decoupled architecture of static and dynamic data streams makes maintenance highly efficient.

**Long-term Value:**
The system can be easily embedded into e-commerce websites as a Customer Support (Live Chat) feature, or serve as a solid foundation to evolve into an internal corporate social network.