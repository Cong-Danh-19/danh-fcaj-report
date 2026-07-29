---
title: "Tạo HTTP API (REST)"
date: 2026-07-28
weight: 6
chapter: false
pre: " <b> 5.6.1 </b> "
---
#### 5.6.1. Tạo HTTP API (REST)

HTTP API được dùng để tải lịch sử chat, danh sách phòng, danh sách người dùng và sinh link tải ảnh (S3 Presigned URL).

1. Truy cập **API Gateway** trên AWS Console, nhấn **Create API** và chọn **Build** ở phần **HTTP API**.
![HTTP API](/images/5-Workshop/5.6-API-gateway/Screenshot1.png)

2. Đặt tên cho API (VD: `ChatRestAPI`) và nhấn tạo.
![HTTP API](/images/5-Workshop/5.6-API-gateway/Screenshot2.png)
![HTTP API](/images/5-Workshop/5.6-API-gateway/Screenshot3.png)
3. Ở menu bên trái, chọn **Routes** và nhấn **Create**.
![HTTP API](/images/5-Workshop/5.6-API-gateway/Screenshot4.png)

4. Chọn Method là **GET** và nhập Path là `/messages`, sau đó nhấn Create.
![HTTP API](/images/5-Workshop/5.6-API-gateway/Screenshot5.png)

5. Chuyển sang mục **Integrations**, chọn route `GET /messages` vừa tạo, nhấn **Attach integration** -> **Create and attach an integration**.
6. Chọn loại tích hợp là **Lambda function**, tìm và chọn hàm `GetMessagesHandler` của bạn, sau đó nhấn Create.
![HTTP API](/images/5-Workshop/5.6-API-gateway/Screenshot6.png)

**Bước cực kỳ quan trọng: Cấu hình CORS**
Vì giao diện React được host trên một domain khác, chúng ta bắt buộc phải bật CORS (Cross-Origin Resource Sharing) để trình duyệt không chặn kết nối.
* Chọn mục **CORS** ở menu bên trái.
* Tại **Access-Control-Allow-Origins**, nhập `*` và nhấn Add.
* Tại **Access-Control-Allow-Methods**, nhập `*` và nhấn Add.
* Tại **Access-Control-Allow-Headers**, nhập `*` và nhấn Add.
* Nhấn **Save**.

![HTTP API](/images/5-Workshop/5.6-API-gateway/Screenshot7.png)
