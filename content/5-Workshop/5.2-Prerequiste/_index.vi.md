---
title: "Điều kiện tiên quyết"
date: 2026-07-27
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

### Những gì bạn cần chuẩn bị

Trước khi bắt đầu các bước thực hành của workshop, hãy đảm bảo bạn đã chuẩn bị sẵn sàng các điều kiện sau:

**1. Tài khoản AWS**
* Bạn cần có một tài khoản AWS đang hoạt động.
* Bạn cần sử dụng IAM User hoặc IAM Role có quyền **AdministratorAccess** (hoặc đủ quyền để tạo và quản lý Cognito, DynamoDB, Lambda, API Gateway, S3, CloudFront và IAM).
* *Lưu ý: Theo tiêu chuẩn bảo mật của AWS, tuyệt đối không nên sử dụng tài khoản Root để thực hành.*

**2. Thống nhất Khu vực (Region)**
* Để tránh lỗi kết nối chéo khu vực (ví dụ: Lambda ở region này không tìm thấy bảng DynamoDB ở region khác), bạn bắt buộc phải chọn **một Region duy nhất** cho toàn bộ tài nguyên.
* Khu vực khuyến nghị: **Singapore (`ap-southeast-1`)** hoặc **Sydney (`ap-southeast-2`)**.

**3. Môi trường phát triển Local**
* Một trình soạn thảo mã nguồn, khuyến nghị sử dụng [Visual Studio Code (VS Code)](https://code.visualstudio.com/).
* **Node.js và npm** đã được cài đặt trên máy tính để chạy và đóng gói giao diện ReactJS. Có thể tải về tại [nodejs.org](https://nodejs.org/).

**4. Mã nguồn (Source Code)**
* Mã nguồn tĩnh của giao diện Frontend ReactJS (`App.jsx`, `App.css`,...) đã được chuẩn bị sẵn. Bạn sẽ sử dụng [mã nguồn](https://github.com/khoaph4mj/aws-serverless-chat-app) này để gắn các đường link API của AWS vào ở những bước sau.


Khi đã chuẩn bị đầy đủ các điều kiện trên, bạn đã sẵn sàng bước vào phần thực hành đầu tiên: **Xác thực người dùng với Amazon Cognito**.