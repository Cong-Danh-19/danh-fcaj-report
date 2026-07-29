---
title: "Tải file lên AWS"
date: 2026-07-28
weight: 8
chapter: false
pre: " <b> 5.8.4 </b> "
---

#### 5.8.4. Tải file lên AWS
1. Chuyển sang tab **Objects** trong bucket của bạn và nhấn **Upload**.
2. Mở thư mục `dist` trên máy tính. **Chọn tất cả các file và thư mục BÊN TRONG thư mục `dist`** (tuyệt đối không kéo nguyên cái vỏ thư mục `dist` vào, chỉ kéo các thành phần bên trong nó như `index.html` và folder `assets`).
3. Kéo thả chúng vào giao diện AWS và nhấn **Upload**.
![S3 web hosting](/images/5-Workshop/5.8-S3-Web-hosting/Screenshot10.png)

Nếu bạn truy cập vào đường link **Bucket website endpoint** đã copy lúc nãy, bạn sẽ thấy ứng dụng web của mình đang chạy trực tuyến! Ở bước tiếp theo, chúng ta sẽ thêm CloudFront để có tốc độ tải nhanh hơn và bảo mật HTTPS.