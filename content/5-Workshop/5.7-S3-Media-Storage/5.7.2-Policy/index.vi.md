---
title : "Cấu hình Bucket Policy"
date : 2026-07-27
weight : 7
chapter : false
pre : " <b> 5.7.2 </b> "
---

#### 5.7.2. Cấu hình Bucket Policy (Quyền đọc công khai)

Chúng ta cần cho phép trình duyệt web đọc và hiển thị các hình ảnh được lưu trong bucket này.

1. Bấm vào bucket vừa tạo và chuyển sang tab **Permissions** (Quyền).
![DynamoDB Tables](/images/5-Workshop/5.7-S3-Media-Storage/Screenshot5.PNG)

2. Cuộn xuống mục **Bucket policy** và nhấn **Edit**.
![DynamoDB Tables](/images/5-Workshop/5.7-S3-Media-Storage/Screenshot6.PNG)

3. Dán chính sách JSON sau vào. **Quan trọng: Thay thế `YOUR_BUCKET_NAME` bằng tên bucket thực tế của bạn.**

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicRead",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*"
        }
    ]
}
```
![DynamoDB Tables](/images/5-Workshop/5.7-S3-Media-Storage/Screenshot7.PNG)

4.  Nhấn Save changes.
![DynamoDB Tables](/images/5-Workshop/5.7-S3-Media-Storage/Screenshot8.PNG)