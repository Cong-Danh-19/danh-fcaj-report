---
title: "Nhật ký công việc tuần 7"
date: 2026-07-13
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---
### Mục tiêu tuần 7:

* Tìm hiểu và tích hợp AWS S3 để lưu trữ file/hình ảnh.
* Tìm hiểu và tích hợp dịch vụ cơ sở dữ liệu được quản lý của AWS (RDS/DynamoDB) cho ứng dụng.

### Các nhiệm vụ cần thực hiện trong tuần này:
| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu các khái niệm của S3<br>&emsp; + Bucket<br>&emsp; + Object<br>&emsp; + Quyền truy cập<br>- Tạo S3 bucket, cấu hình bucket policy & CORS | 13/07/2026 | 13/07/2026 | https://docs.aws.amazon.com/s3/ |
| 3 | - Tích hợp AWS SDK vào backend để upload/download file<br>- Triển khai chức năng upload file (hình ảnh, tài liệu) sử dụng S3 | 14/07/2026 | 14/07/2026 |  |
| 4 | - Nghiên cứu RDS và DynamoDB, so sánh với cơ sở dữ liệu tự triển khai<br>- Tạo RDS instance / DynamoDB table, cấu hình bảo mật | 15/07/2026 | 15/07/2026 | https://docs.aws.amazon.com/rds/ |
| 5 | - Di chuyển schema/dữ liệu sang cơ sở dữ liệu được quản lý<br>- Cập nhật ứng dụng backend để kết nối với dịch vụ cơ sở dữ liệu mới | 16/07/2026 | 16/07/2026 |  |
| 6 | - Kiểm thử upload/download file và kết nối cơ sở dữ liệu<br>- Tối ưu truy cập file (presigned URL) và theo dõi hiệu năng cơ sở dữ liệu | 17/07/2026 | 17/07/2026 |  |

### Thành tích tuần 7:

* Hiểu được các khái niệm cốt lõi của S3 và tạo được S3 bucket cấu hình đúng.
* Triển khai chức năng upload/download file sử dụng AWS SDK và S3.
* Hiểu được sự khác biệt giữa RDS và DynamoDB và khi nào nên sử dụng từng loại.
* Tạo và bảo mật database instance/table được quản lý, di chuyển dữ liệu sang đó.
* Cập nhật ứng dụng backend để hoạt động với S3 và cơ sở dữ liệu mới, xác nhận qua kiểm thử.
