---
title: "Kho lưu trữ ảnh S3"
date: 2026-07-27
weight: 7
chapter: false
pre: " <b> 5.7. </b> "
---

#### Mục tiêu
Trong bước này, chúng ta sẽ tạo một **Amazon S3 Bucket** để lưu trữ các file hình ảnh do người dùng gửi trong phòng chat. Để tối ưu hóa hiệu suất và chi phí, chúng ta sử dụng **Presigned URLs**. Phương pháp này cho phép giao diện React tải các file nặng trực tiếp lên S3, hoàn toàn bỏ qua AWS Lambda để tránh lỗi giới hạn dung lượng tải trọng (payload limit) và quá thời gian thực thi (timeout).

#### Nội dung

1. [Tạo S3 Bucket](5.7.1-create-S3)
2. [Cấu hình Bucket Policy](5.7.2-Policy/)
3. [Cấu hình CORS](5.7.3-CORS/)
