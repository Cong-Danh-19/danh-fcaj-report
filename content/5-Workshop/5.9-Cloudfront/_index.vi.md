---
title: "Phân phối với CloudFront"
date: 2026-07-29
weight: 9
chapter: false
pre: " <b> 5.9. </b> "
---

#### Mục tiêu
Ở bước triển khai cuối cùng này, chúng ta sẽ sử dụng **Amazon CloudFront**, một Mạng phân phối nội dung (CDN) toàn cầu, để đưa website ra Internet một cách bảo mật. CloudFront sẽ lưu trữ bộ nhớ đệm (cache) các file React tĩnh tại các máy chủ biên (edge locations) trên toàn thế giới để mang lại độ trễ cực thấp, đồng thời cung cấp mã hóa **HTTPS** mặc định cho ứng dụng.

1. [Tạo CloudFront Distribution](5.9.1-cloudfront-dist/)
2. [Trải nghiệm Ứng dụng Thực tế](5.9.2-access/)
