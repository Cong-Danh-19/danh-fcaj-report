---
title : "Tại sao lại chọn Amazon DynamoDB?"
date : 2026-07-28
weight : 4
chapter : false
pre : " <b> 5.4.1 </b> "
---

### 5.4.1. Tại sao lại chọn Amazon DynamoDB?
Đối với một ứng dụng chat thời gian thực, tốc độ và khả năng mở rộng là yếu tố sống còn. Chúng tôi chọn DynamoDB thay vì các cơ sở dữ liệu quan hệ truyền thống (như MySQL) bởi vì:
* **Thuần Serverless:** Không có máy chủ nào cần phải cấu hình, cài đặt hay bảo trì.
* **Hiệu suất cực cao:** DynamoDB cung cấp thời gian phản hồi ổn định ở mức mili-giây (single-digit millisecond) ở bất kỳ quy mô nào, cực kỳ phù hợp cho ứng dụng nhắn tin.
* **Lược đồ linh hoạt (Flexible Schema):** Là cơ sở dữ liệu NoSQL, nó dễ dàng xử lý các thuộc tính dữ liệu chat luôn thay đổi (VD: tin nhắn có ảnh hoặc không có ảnh).




