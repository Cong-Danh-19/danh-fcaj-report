---
title: "Thiết lập Bảo mật IAM Role"
date: 2026-07-27
weight: 5
chapter: false
pre: " <b> 5.5.1 </b> "
---

#### 5.5.1. Thiết lập Bảo mật IAM Role

Trước khi tạo hàm Lambda, chúng ta phải cấp cho nó những quyền chính xác để có thể tương tác với các dịch vụ AWS khác.

1. Vào dịch vụ **IAM** trên AWS Console, chọn **Roles**, và nhấn **Create role**.
![IAM Role Setup](images/Screenshot1.png)

2. Chọn **AWS service** làm thực thể tin cậy (trusted entity) và **Lambda** ở mục use case.
![IAM Role Setup](images/Screenshot2.png)

3. Gắn các quyền (policies) sau vào Role:
   * `AmazonDynamoDBFullAccess` *(Để đọc/ghi dữ liệu chat)*
   * `AmazonS3FullAccess` *(Để tạo Presigned URL up ảnh)*
   * `AmazonCognitoReadOnly` *(Để lấy danh sách user từ Cognito)*
   * `AmazonAPIGatewayInvokeFullAccess` *(Để gửi tin nhắn WebSocket ngược về trình duyệt)*
   * `AWSLambdaBasicExecutionRole` *(Để ghi log hệ thống lên CloudWatch)*
![IAM Role Setup](images/Screenshot3.png)
![IAM Role Setup](images/Screenshot4.png)
![IAM Role Setup](images/Screenshot5.png)
![IAM Role Setup](images/Screenshot6.png)
![IAM Role Setup](images/Screenshot7.png)
4. Nhấn vào **Next**
5. Đặt tên Role là **`ChatApp_Lambda_Role`**, review lại **Permissions policies** và nhấn tạo.

![IAM Role Setup](images/Screenshot8.png)
![IAM Role Setup](images/Screenshot9.png)
