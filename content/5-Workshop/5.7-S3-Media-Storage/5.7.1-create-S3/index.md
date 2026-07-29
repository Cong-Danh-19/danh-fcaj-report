---
title : "Create the S3 Bucket"
date : 2026-07-27
weight : 7
chapter : false
pre : " <b> 5.7.1 </b> "
---

#### 5.7.1. Create the S3 Bucket
1. Navigate to the **Amazon S3** service in the AWS Console and click **Create bucket**.
![DynamoDB Tables](/images/5-Workshop/5.7-S3-Media-Storage/Screenshot1.PNG)

2. **Bucket name:** Enter a globally unique name (e.g., `chatapp-images-2026`). Save this name, as you will need it later.

3. **Object Ownership:** Select **ACLs disabled (recommended)**.
![DynamoDB Tables](/images/5-Workshop/5.7-S3-Media-Storage/Screenshot2.PNG)

4. **Block Public Access settings:** 
   * **Uncheck** the *Block all public access* option.
   * Check the acknowledgment box warning that objects might become public. (We need this so users can view the images in the chat).
![DynamoDB Tables](/images/5-Workshop/5.7-S3-Media-Storage/Screenshot3.PNG)

5. Scroll to the bottom and click **Create bucket**.
![DynamoDB Tables](/images/5-Workshop/5.7-S3-Media-Storage/Screenshot4.PNG)

