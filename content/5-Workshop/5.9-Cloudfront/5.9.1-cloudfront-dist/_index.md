---
title: "Global Delivery with CloudFront"
date: 2026-07-29
weight: 9
chapter: false
pre: " <b> 5.9.1 </b> "
---

#### 5.9.1. Create a CloudFront Distribution

1. Navigate to the **CloudFront** service in the AWS Console and click **Create a CloudFront distribution**.
![Cloudfront](/images/5-Workshop/5.9-Cloudfront/Screenshot1.png)
2. Named the distribution **`aws-chatapp-dist`**, descripted **`chatapp`**, then click on **Next**.
2. **Origin domain:** 
   * Paste the **Bucket website endpoint** (the HTTP link) that you copied from the S3 Static Website Hosting settings in the previous step. Remove the `http://` prefix. (e.g., `chatapp-frontend-2026.s3-website-ap-southeast-2.amazonaws.com`).
3. Click on **Next**.
![Cloudfront](/images/5-Workshop/5.9-Cloudfront/Screenshot2.png)
4. Under **Web Application Firewall (WAF)**:
   * Select **Do not enable security protections** (to keep the setup simple and free).
![Cloudfront](/images/5-Workshop/5.9-Cloudfront/Screenshot3.png)
5. Click **Create distribution**.

