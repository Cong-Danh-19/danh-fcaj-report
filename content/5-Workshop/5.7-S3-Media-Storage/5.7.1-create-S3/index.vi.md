---
title : "Tạo Bucket S3"
date : 2026-07-27
weight : 7
chapter : false
pre : " <b> 5.7.1 </b> "
---
#### 5.7.1. Tạo Bucket S3

1. Truy cập dịch vụ **Amazon S3** trên AWS Console và nhấn **Create bucket**.
![DynamoDB Tables](/images/5-Workshop/5.7-S3-Media-Storage/Screenshot1.PNG)

2. **Bucket name:** Nhập một tên duy nhất trên toàn cầu (VD: `chatapp-images-2026`). Hãy nhớ tên này vì bạn sẽ cần dùng lại nó.
3. **Object Ownership:** Chọn **ACLs disabled (recommended)**.
![DynamoDB Tables](/images/5-Workshop/5.7-S3-Media-Storage/Screenshot2.PNG)

4. **Cài đặt Block Public Access:** 
   * **Bỏ chọn** (Uncheck) ô *Block all public access*.
   * Tick vào ô xác nhận cảnh báo rằng các file có thể hiển thị công khai. (Chúng ta cần điều này để người dùng có thể xem ảnh trong khung chat).
![DynamoDB Tables](/images/5-Workshop/5.7-S3-Media-Storage/Screenshot3.PNG)

5. Cuộn xuống cuối trang và nhấn **Create bucket**.
![DynamoDB Tables](/images/5-Workshop/5.7-S3-Media-Storage/Screenshot4.PNG)

