---
title: "Prerequisites"
date: 2026-07-27
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

### What you need before starting

Before diving into the workshop, ensure you have the following requirements ready:

**1. AWS Account**
* You must have an active AWS account.
* You need an IAM User or IAM Role with **AdministratorAccess** (or sufficient permissions to create and manage Cognito, DynamoDB, Lambda, API Gateway, S3, CloudFront, and IAM resources).
* *Note: Using the Root User is strongly discouraged by AWS best practices.*

**2. Unified Region**
* To avoid cross-region connection errors (e.g., Lambda in one region unable to find a DynamoDB table in another), you must select **one specific region** for all your resources.
* Recommended regions: **Singapore (`ap-southeast-1`)** or **Sydney (`ap-southeast-2`)**.

**3. Local Development Environment**
* A code editor, such as [Visual Studio Code (VS Code)](https://code.visualstudio.com/).
* **Node.js and npm** installed on your machine to configure and build the ReactJS frontend. You can download it from [nodejs.org](https://nodejs.org/).

**4. Source Code**
* The boilerplate code for the ReactJS Frontend (`App.jsx`, `App.css`, etc.) has been prepared in advance. You will use this [code](https://github.com/khoaph4mj/aws-serverless-chat-app) to integrate the AWS API endpoints during the lab.


Once you have these prerequisites set up, you are ready to move on to the first step: **Authentication with Amazon Cognito**.