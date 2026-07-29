---
title : "Configure CORS"
date : 2026-07-27
weight : 7
chapter : false
pre : " <b> 5.7.3 </b> "
---

####5.7.3. Cấu hình CORS (Cross-Origin Resource Sharing)

Nếu không có CORS, trình duyệt sẽ chặn không cho phép Frontend gửi file trực
tiếp lên S3.

1.  Vẫn ở tab Permissions, cuộn xuống dưới cùng để tìm mục Cross-origin resource
    sharing (CORS).
![DynamoDB Tables](images/Screenshot9.PNG)

2.  Nhấn Edit và dán cấu hình JSON sau đây:

```json
[
    {
        "AllowedHeaders": ["*"],
        "AllowedMethods": ["PUT", "GET"],
        "AllowedOrigins": ["*"],
        "ExposeHeaders": []
    }
]
```
![DynamoDB Tables](images/Screenshot10.PNG)

3.  Nhấn Save changes.
![DynamoDB Tables](images/Screenshot11.PNG)