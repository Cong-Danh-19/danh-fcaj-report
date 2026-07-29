---
title: "Tạo CloudFront Distribution"
date: 2026-07-29
weight: 9
chapter: false
pre: " <b> 5.9.1 </b> "
---

#### 5.9.1. Tạo CloudFront Distribution

1. Truy cập dịch vụ **CloudFront** trên AWS Console và nhấn **Create a CloudFront distribution**.
![Cloudfront](/images/5-Workshop/5.9-Cloudfront/Screenshot1.png)
2. Đặt tên phân phối là **`aws-chatapp-dist`**, mô tả là **`chatapp`**, rồi nhấn vào **Next**.
2. **Origin domain (Tên miền gốc):** 
   * Dán đường link **Bucket website endpoint** (đường link HTTP) mà bạn đã copy ở phần S3 Static Website Hosting trong bước trước vào đây. Hãy xóa tiền tố `http://` ở đầu đi. (Ví dụ: `chatapp-frontend-2026.s3-website-ap-southeast-2.amazonaws.com`).
3. Nhấn vào **Next**.
![Cloudfront](/images/5-Workshop/5.9-Cloudfront/Screenshot2.png)
4. Bên dưới **Web Application Firewall (WAF)**:
   * Chọn **Do not enable security protections** (Không bật WAF để tránh các bước cấu hình rườm rà và tiết kiệm chi phí).
![Cloudfront](/images/5-Workshop/5.9-Cloudfront/Screenshot3.png)
5. Nhấn **Create distribution**.

