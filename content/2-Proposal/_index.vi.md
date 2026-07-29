---
title: "Proposal (Đề xuất dự án)"
date: 2026-07-27
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Ứng dụng Chat Thời gian thực với Kiến trúc Serverless Hybrid trên AWS

### 1. Tóm tắt dự án
Dự án "Serverless Hybrid Real-time Chat Application" được thiết kế nhằm cung cấp một nền tảng giao tiếp trực tuyến với độ trễ cực thấp, hỗ trợ phòng chat chung (Global), chat nhóm kín và nhắn tin cá nhân (1-1). Dự án tận dụng tối đa sức mạnh của kiến trúc Serverless trên AWS (API Gateway, Lambda, DynamoDB) kết hợp phương pháp tiếp cận Hybrid: dùng REST API cho dữ liệu tĩnh và WebSocket API cho luồng dữ liệu thời gian thực.

### 2. Tuyên bố vấn đề (Problem Statement)
**Vấn đề hiện tại là gì?**
Các ứng dụng chat truyền thống dựa trên REST API thường gặp độ trễ cao do phải dùng kỹ thuật polling liên tục, gây lãng phí tài nguyên mạng. Ngược lại, việc tự duy trì các máy chủ WebSocket chuyên dụng (như dùng EC2) lại tốn kém chi phí cố định hàng tháng, khó tự động mở rộng (scale) khi lượng người dùng tăng đột biến và lãng phí tài nguyên khi hệ thống rảnh rỗi.

**Giải pháp đề xuất**
Nền tảng này sử dụng kiến trúc 100% Serverless. **Amazon Cognito** quản lý xác thực người dùng. Dữ liệu thời gian thực được xử lý qua **Amazon API Gateway (WebSocket)** và AWS Lambda, duy trì kết nối 2 chiều mà không cần máy chủ ảo. Lịch sử tin nhắn được truy xuất qua **API Gateway (HTTP API)**. Ảnh và file media được tải trực tiếp lên **Amazon S3** thông qua Presigned URL, giúp giảm tải hoàn toàn cho Backend. Giao diện Frontend (ReactJS) được lưu trữ trên S3 và phân phối toàn cầu qua **Amazon CloudFront**.

**Lợi ích và Tỷ suất hoàn vốn (ROI)**
Giải pháp giúp xóa bỏ hoàn toàn chi phí bảo trì máy chủ (Zero Server Maintenance). Tận dụng AWS Free Tier, chi phí vận hành hàng tháng gần như bằng $0 đối với quy mô nghiên cứu. Hệ thống có khả năng tự động mở rộng để phục vụ hàng ngàn kết nối đồng thời mà không cần can thiệp thủ công.

### 3. Kiến trúc giải pháp
Hệ thống sử dụng kiến trúc phân tách (Decoupled Architecture). Frontend giao tiếp với AWS qua 2 cổng riêng biệt: HTTP API (REST) cho các tác vụ nặng/tĩnh và WebSocket API cho các luồng tin nhắn siêu nhẹ. 

*(Chèn hình ảnh sơ đồ kiến trúc vào đây: `![Architecture Diagram](/images/2-Proposal/architecture.jpeg)`)*

**Các dịch vụ AWS sử dụng:**
- **Amazon S3:** Hosting Frontend tĩnh (ReactJS) và làm kho lưu trữ ảnh.
- **Amazon CloudFront:** Mạng phân phối nội dung (CDN) giúp tăng tốc độ tải trang và cung cấp HTTPS.
- **Amazon Cognito:** Quản lý User Pool, xác thực người dùng an toàn.
- **Amazon API Gateway:** Cung cấp cả 2 chuẩn giao tiếp HTTP API (REST) và WebSocket API.
- **AWS Lambda:** Xử lý logic Backend bằng Python (Xử lý kết nối, lưu tin nhắn, sinh Presigned URL).
- **Amazon DynamoDB:** Cơ sở dữ liệu NoSQL lưu trữ danh sách phòng (Rooms), tin nhắn (Messages) và các kết nối đang online (Connections).
- **AWS IAM:** Quản lý phân quyền chặt chẽ theo nguyên tắc Quyền tối thiểu (Least Privilege).

### 4. Triển khai kỹ thuật
**Các giai đoạn triển khai**
- **Giai đoạn 1 (Môi trường & Xác thực):** Khởi tạo môi trường, thiết lập IAM và tích hợp hệ thống xác thực Amazon Cognito vào ReactJS.
- **Giai đoạn 2 (Database & REST Backend):** Thiết kế các bảng DynamoDB và xây dựng HTTP API lấy lịch sử tin nhắn, danh sách người dùng.
- **Giai đoạn 3 (Real-time Engine & Media):** Xây dựng luồng WebSocket API để định tuyến tin nhắn theo phòng (Private/Public) và cấu hình S3 Presigned URL để tải ảnh.
- **Giai đoạn 4 (Frontend & Triển khai):** Tích hợp giao diện ReactJS, kiểm thử End-to-End và đưa website lên Internet bằng CloudFront.

**Yêu cầu kỹ thuật**
- Frontend: ReactJS, giao tiếp qua thư viện `aws-amplify` và `Fetch API`.
- Backend: AWS Lambda viết bằng Python (boto3 SDK).
- Security: Cấu hình CORS nghiêm ngặt trên API Gateway và Bucket Policies.

### 5. Tiến độ & Cột mốc
- **Tháng 1:** Nghiên cứu kiến trúc Serverless, làm quen với Amazon Cognito và thiết kế dữ liệu DynamoDB.
- **Tháng 2:** Phát triển Backend (Lambda, API Gateway) và triển khai cơ chế định tuyến WebSocket.
- **Tháng 3:** Hoàn thiện UI/UX Frontend, tích hợp tính năng gửi ảnh qua S3, kiểm thử lỗi và triển khai sản phẩm lên CloudFront. Viết báo cáo.

### 6. Ước tính ngân sách
Toàn bộ kiến trúc được thiết kế tối ưu để nằm gọn trong **AWS Free Tier**. Chi phí thực tế hàng tháng ước tính là **$0.00**. Ước tính nếu vượt quá Free Tier (Mức tải 10,000 tin nhắn/tháng):
- AWS Lambda: $0.00 (Miễn phí 1 triệu request/tháng).
- Amazon API Gateway: ~$0.05 (Thời gian duy trì WebSocket).
- Amazon DynamoDB: $0.00 (Miễn phí 25 GB lưu trữ).
- Amazon S3 & CloudFront: ~$0.10 (Lưu trữ và truyền tải dữ liệu ảnh).
- **Tổng chi phí ước tính:** < $0.5 / tháng.

### 7. Đánh giá rủi ro
**Ma trận rủi ro:**
- Mất kết nối mạng (WebSocket Drop): Tác động cao, Xác suất trung bình.
- Lỗi bảo mật CORS (Cross-Origin): Tác động cao, Xác suất cao.
- Vượt quá dung lượng xử lý Lambda (Gửi file nặng): Tác động trung bình, Xác suất thấp.

**Chiến lược giảm thiểu:**
- **Mạng:** Thiết kế Frontend (React) tự động kết nối lại khi WebSocket bị ngắt.
- **CORS:** Thiết lập Allow-Origins và Allow-Headers rõ ràng trên API Gateway và S3.
- **Dung lượng file:** Sử dụng S3 Presigned URL để Client tải file thẳng lên S3, chỉ truyền link text qua WebSocket, giảm tải 100% cho Lambda.

### 8. Kết quả mong đợi
**Cải tiến kỹ thuật:** 
Nền tảng nhắn tin không cần duy trì máy chủ, tiết kiệm tài nguyên khi không có người dùng. Độ trễ phản hồi khi nhắn tin cực thấp. Phân tách rõ ràng luồng dữ liệu tĩnh và động giúp dễ dàng bảo trì.

**Giá trị dài hạn:**
Hệ thống có thể dễ dàng được nhúng vào các website thương mại điện tử làm tính năng Hỗ trợ khách hàng (Live Chat), hoặc làm nền tảng cơ sở vững chắc để phát triển thành một ứng dụng mạng xã hội nội bộ cho doanh nghiệp.