---
title: "Build the React Application"
date: 2026-07-28
weight: 8
chapter: false
pre: " <b> 5.8.1 </b> "
---

#### 5.8.1. Đóng gói (Build) ứng dụng React

Trước khi tải lên AWS, chúng ta cần biên dịch mã nguồn React thành các file HTML, CSS và JS tĩnh.

1. Đảm bảo bạn đã thay thế tất cả các phần `TODO` trong file `App.jsx` bằng các mã ID của Cognito, URL của HTTP API và URL của WebSocket API của bạn.
2. Mở terminal trong trình soạn thảo code (như VS Code) và tắt server chạy local nếu nó đang bật (Nhấn `Ctrl + C`).
3. Chạy câu lệnh sau:
```bash
    npm run build
```
4. Đợi vài giây. Một thư mục mới có tên là **`dist`** sẽ được tạo ra trong thư mục dự án của bạn. Thư mục này chứa toàn bộ trang web đã được tối ưu hóa.