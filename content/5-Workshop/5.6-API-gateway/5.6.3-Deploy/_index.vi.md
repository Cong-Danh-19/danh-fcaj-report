---
title: "Triển khai & Tích hợp vào Giao diện"
date: 2026-07-28
weight: 6
chapter: false
pre: " <b> 5.6.3 </b> "
---

#### 5.6.3. Triển khai & Tích hợp vào Giao diện

Sau khi cả 2 API được tạo và triển khai, bạn cần lấy đường dẫn (URL) của chúng để gắn vào giao diện Frontend.

1. Đối với **HTTP API**: Vào mục **Stages**, chọn stage `default`, và sao chép đường dẫn Invoke URL (bắt đầu bằng `https://...`). Nhớ thêm `/messages` vào đuôi khi dán vào code React.
![Integration](/images/5-Workshop/5.6-API-gateway/Screenshot13.png)


2. Đối với **WebSocket API**: Vào mục **Stages**, chọn stage `production`, và sao chép đường dẫn WebSocket URL (bắt đầu bằng `wss://...`).
![Integration](/images/5-Workshop/5.6-API-gateway/Screenshot14.png)

Cập nhật file `App.jsx` trong mã nguồn React của bạn bằng 2 đường link này. Vậy là Frontend của bạn đã kết nối thành công với AWS Backend!
```javascript
const REST_URL = "https://.../messages";
const WSS_URL_BASE = "wss://.../production/";