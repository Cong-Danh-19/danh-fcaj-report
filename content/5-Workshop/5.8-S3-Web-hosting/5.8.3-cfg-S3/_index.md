---
title: "Enable Static Website Hosting & Bucket Policy"
date: 2026-07-28
weight: 8
chapter: false
pre: " <b> 5.8.3 </b> "
---

#### 5.8.3. Enable Static Website Hosting & Bucket Policy
1. Click on your newly created frontend bucket and navigate to the **Properties** tab.
![S3 web hosting](images/Screenshot5.png)
2. Scroll to the very bottom and click **Edit** under **Static website hosting**.
![S3 web hosting](images/Screenshot6.png)
![S3 web hosting](images/Screenshot7.png)

3. Select **Enable**.
4. Set both the **Index document** and **Error document** to **`index.html`**. *(Setting the error document to index.html is crucial for Single-Page Applications like React so that direct URL access doesn't return a 404 error)*.
![S3 web hosting](images/Screenshot8.png)

5. Click **Save changes**. Note down the **Bucket website endpoint** provided here.
6. Now, switch to the **Permissions** tab. Scroll to **Bucket policy**, click **Edit**, and paste the following JSON *(replace **`YOUR_FRONTEND_BUCKET_NAME`** with your actual bucket name)*:
![S3 web hosting](images/Screenshot9.png)

```JSON
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicRead",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::YOUR_FRONTEND_BUCKET_NAME/*"
        }
    ]
}
```

7. Click **Save changes**.

