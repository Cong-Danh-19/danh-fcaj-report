---
title: "Image Storage with S3"
date: 2026-07-27
weight: 7
chapter: false
pre: " <b> 5.7. </b> "
---

#### Objective
In this step, we will create an **Amazon S3 Bucket** to store image files sent by users in the chat rooms. To optimize performance and cost, we use **Presigned URLs**. This approach allows the React frontend to upload large files directly to S3, completely bypassing AWS Lambda to prevent payload size limits and execution timeouts.

#### Content

1. [Create the S3 Bucket](5.7.1-create-S3)
2. [Configure Bucket Policy](5.7.2-Policy/)
3. [Configure CORS](5.7.3-CORS/)

