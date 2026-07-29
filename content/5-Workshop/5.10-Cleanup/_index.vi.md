---
title: "Dọn dẹp tài nguyên"
date: 2026-07-29
weight: 10
chapter: false
pre: " <b> 5.10. </b> "
---

### Mục tiêu
Chúc mừng bạn đã xây dựng thành công Ứng dụng Chat Serverless Hybrid Real-time!

Để tránh việc phát sinh các khoản phí ngoài ý muốn trên hóa đơn AWS sau khi hoàn thành bài thực hành này, việc xóa bỏ toàn bộ tài nguyên đã tạo là bắt buộc. **Luôn xóa tài nguyên theo thứ tự từ ngoài vào trong** (Frontend -> APIs -> Backend -> Database) để tránh các lỗi ràng buộc lẫn nhau.

---

### Hướng dẫn Dọn dẹp từng bước

**1. Amazon CloudFront**
* Truy cập giao diện **CloudFront**.
* Chọn Distribution của bạn và nhấn **Disable** (Vô hiệu hóa).
* *Lưu ý: Bạn phải chờ vài phút để trạng thái chuyển sang "Disabled" (Đã vô hiệu hóa) thì mới có thể chọn lại và nhấn nút **Delete** (Xóa).*
![Cleanup](/images/5-Workshop/5.10-Cleanup/1.png)

**2. Amazon S3 (Bucket Frontend và Bucket Ảnh)**
* Truy cập giao diện **S3**.
* Bạn không thể xóa một bucket đang chứa file. Đầu tiên, chọn bucket frontend của bạn, nhấn **Empty** (Làm rỗng) và xác nhận xóa toàn bộ các object bên trong.
* Khi bucket đã rỗng, chọn lại bucket đó và nhấn **Delete** (Xóa).
* Lặp lại quy trình y hệt (Empty -> Delete) đối với bucket lưu trữ ảnh của bạn.
![Cleanup](/images/5-Workshop/5.10-Cleanup/2.png)

**3. Amazon API Gateway**
* Truy cập giao diện **API Gateway**.
* Chọn **HTTP API** (`ChatRestAPI`) của bạn và nhấn **Delete**.
* Chọn **WebSocket API** (`ChatWebSocketAPI`) của bạn và nhấn **Delete**.
![Cleanup](/images/5-Workshop/5.10-Cleanup/3.png)

**4. AWS Lambda**
* Truy cập giao diện **Lambda**.
* Chọn hàm `RealtimeChatHandler`, nhấn **Actions** -> **Delete**.
* Chọn hàm `GetMessagesHandler`, nhấn **Actions** -> **Delete**.
![Cleanup](/images/5-Workshop/5.10-Cleanup/4.png)

**5. Amazon DynamoDB**
* Truy cập giao diện **DynamoDB** và chọn **Tables**.
* Chọn bảng `Connections` và nhấn **Delete**.
* Chọn bảng `Rooms` và nhấn **Delete**.
* Chọn bảng `Messages` và nhấn **Delete**.
![Cleanup](/images/5-Workshop/5.10-Cleanup/5.png)

**6. Amazon Cognito**
* Truy cập giao diện **Cognito** và chọn **User pools**.
* Chọn User Pool của bạn (VD: `ChatAppClient`) và nhấn **Delete**. Bạn sẽ cần gõ lại tên của User Pool để xác nhận xóa.
![Cleanup](/images/5-Workshop/5.10-Cleanup/6.png)
**7. AWS IAM**
* Truy cập giao diện **IAM** và chọn mục **Roles**.
* Tìm kiếm Role mang tên `ChatApp_Lambda_Role`, chọn nó và nhấn **Delete**.
![Cleanup](/images/5-Workshop/5.10-Cleanup/7.png)

***Workshop Hoàn Tất! Cảm ơn bạn đã đồng hành cùng hành trình Kiến trúc Serverless này.***