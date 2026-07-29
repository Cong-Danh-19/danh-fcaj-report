---
title: "Tạo WebSocket API"
date: 2026-07-28
weight: 6
chapter: false
pre: " <b> 5.6.2 </b> "
---

#### 5.6.2. Tạo WebSocket API

WebSocket API duy trì kết nối liên tục để phát sóng (broadcast) tin nhắn ngay lập tức.

1. Quay lại trang chủ **API Gateway**, nhấn **Create API** và chọn **Build** ở phần **WebSocket API**.
![Websocket API](/images/5-Workshop/5.6-API-gateway/Screenshot8.png)

2. Đặt tên API (VD: `ChatWebSocketAPI`).
3. Tại ô **Route selection expression**, nhập chính xác chuỗi: `$request.body.action`. *(Điều này giúp API biết cách định tuyến tin nhắn dựa trên nội dung JSON gửi lên).*
![Websocket API](/images/5-Workshop/5.6-API-gateway/Screenshot9.png)

4. Nhấn Next. Ở bước **Add routes**, nhấn **Add route** và tạo một route tên là `sendMessage`. (Các route `$connect` và `$disconnect` đã có sẵn).
![Websocket API](/images/5-Workshop/5.6-API-gateway/Screenshot10.png)
5. Ở bước **Attach integrations**, chọn loại tích hợp là **Lambda** cho cả 3 routes (`$connect`, `$disconnect`, và `sendMessage`), đồng thời chọn hàm `RealtimeChatHandler` cho cả 3.
![Websocket API](/images/5-Workshop/5.6-API-gateway/Screenshot11.png)
6. Tiếp tục các bước còn lại và nhấn **Create and deploy**.
![Websocket API](/images/5-Workshop/5.6-API-gateway/Screenshot12.png)