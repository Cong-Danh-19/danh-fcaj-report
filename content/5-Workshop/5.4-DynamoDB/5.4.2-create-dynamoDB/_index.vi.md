---
title: "Thiết lập Cơ sở dữ liệu"
date: 2026-07-28
weight: 4
chapter: false
pre: " <b> 5.4.2 </b> "
---

#### 5.4.2. Khởi tạo các Bảng (Tables)

Truy cập dịch vụ **DynamoDB** trên AWS Console và nhấn **Create table**. Bạn cần tạo **3 bảng riêng biệt** với tên và khóa chính (Partition/Sort key) chính xác như dưới đây (Lưu ý: Phân biệt chữ hoa chữ thường):

**1. Bảng `Connections`**
* **Table name:** `Connections`
* **Partition key:** `connectionID` (Kiểu String)
* *Mục đích:* Lưu trữ tạm thời ID của những người dùng đang mở kết nối WebSocket. Điều này giúp backend biết chính xác phải phát sóng (broadcast) tin nhắn đến thiết bị nào.

**2. Bảng `Rooms`**
* **Table name:** `Rooms`
* **Partition key:** `roomID` (Kiểu String)
* *Mục đích:* Lưu thông tin chi tiết về các phòng chat, bao gồm tên phòng và danh sách thành viên (để hỗ trợ tính năng chat riêng tư và chat nhóm).
![DynamoDB Tables](/images/5-Workshop/5.4-DynamoDB/Screenshot2.PNG)

**3. Bảng `Messages`**
* **Table name:** `Messages`
* **Partition key:** `roomID` (Kiểu String)
* **Sort key:** `timestamp` (Kiểu Number)
* *Mục đích:* Lưu trữ lịch sử tin nhắn. Khóa sắp xếp (Sort key) `timestamp` cực kỳ quan trọng ở đây vì nó cho phép chúng ta dễ dàng truy vấn và sắp xếp tin nhắn theo trình tự thời gian từ cũ đến mới.
![DynamoDB Tables](/images/5-Workshop/5.4-DynamoDB/Screenshot4.PNG)

Ở phần cài đặt dung lượng (Capacity settings), bạn có thể giữ nguyên mặc định là **Provisioned** để đảm bảo không vượt quá giới hạn của AWS Free Tier.

![DynamoDB Tables](/images/5-Workshop/5.4-DynamoDB/Screenshot5.PNG)

Chờ vài giây cho đến khi trạng thái của cả ba bảng chuyển sang **Active**. Tầng cơ sở dữ liệu của chúng ta đã hoàn tất!
![DynamoDB Tables](/images/5-Workshop/5.4-DynamoDB/Screenshot6.png)
