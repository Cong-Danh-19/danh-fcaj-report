---
title: "Workshop"
date: 2026-07-27
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Xây dựng Ứng dụng Chat thời gian thực với kiến trúc Serverless Hybrid

#### Tổng quan

**Kiến trúc Serverless (Không máy chủ)** cho phép bạn xây dựng và chạy các ứng dụng mà không cần bận tâm về máy chủ. Nó loại bỏ các tác vụ quản lý cơ sở hạ tầng như cung cấp tài nguyên, vá lỗi, bảo trì hệ điều hành và quản lý dung lượng.

Trong bài lab này, bạn sẽ học cách xây dựng một ứng dụng chat thời gian thực hoàn chỉnh bằng phương pháp **Hybrid API** trên AWS. Chúng ta sẽ kết hợp giữa REST API (để truy xuất dữ liệu tĩnh) và WebSocket API (để giao tiếp 2 chiều với độ trễ cực thấp).

Bạn sẽ cấu hình và tích hợp hàng loạt các dịch vụ AWS:
+ **Amazon Cognito** - Để xác thực và quản lý đăng ký người dùng an toàn.
+ **Amazon DynamoDB** - Để lưu trữ tin nhắn, thông tin phòng chat và ID các kết nối đang hoạt động.
+ **AWS Lambda** - Để thực thi logic backend cho cả REST và WebSocket API.
+ **Amazon API Gateway** - Định tuyến lưu lượng truy cập từ giao diện người dùng đến các hàm backend.
+ **Amazon S3** - Làm máy chủ lưu trữ giao diện React và kho lưu trữ file an toàn thông qua Presigned URL.
+ **Amazon CloudFront** - Phân phối ứng dụng toàn cầu với tốc độ cao và bảo mật HTTPS.

#### Nội dung

1. [Tổng quan](5.1-Overview/)
2. [Điều kiện tiên quyết](5.2-Prerequisites/)
3. [Bước 1: Xác thực với Cognito](5.3-Cognito-Auth/)
4. [Bước 2: Thiết lập Cơ sở dữ liệu](5.4-DynamoDB/)
5. [Bước 3: Xử lý Backend & IAM](5.5-Lambda-backend/)
6. [Bước 4: Định tuyến Cổng giao tiếp](5.6-API-gateway/)
7. [Bước 5: Kho lưu trữ ảnh S3](5.7-S3-Media-Storage/)
8. [Bước 6: Lưu trữ Website với S3](5.8-S3-Web-hosting/)
9. [Bước 7: Phân phối toàn cầu với CloudFront](5.9-Cloudfront/)
10. [Dọn dẹp tài nguyên](5.10-Cleanup/)