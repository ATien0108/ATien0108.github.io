---
title: "EC2"
date: 2025-07-09
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

## Tổng quan

**Amazon EC2 (Elastic Compute Cloud)** là dịch vụ máy chủ ảo của AWS cho phép bạn chạy ứng dụng một cách linh hoạt, linh động và theo nhu cầu thực tế. Trong đề tài này, EC2 được sử dụng để triển khai ứng dụng backend.

Các bước thực hiện chính bao gồm:

- **Khởi tạo instance EC2**: Chọn hệ điều hành, cấu hình phần cứng, cài đặt cặp khóa bảo mật và gán vào mạng VPC phù hợp.

- **Kết nối và thiết lập môi trường**: SSH vào instance, cài Node.js, Git và các thư viện cần thiết để chạy ứng dụng backend Node.js.

- **Quản lý tiến trình bằng PM2**: Giúp chạy server ở chế độ nền và tự động khởi động lại khi máy chủ reboot.

Việc nắm vững thao tác với EC2 sẽ giúp bạn triển khai ứng dụng một cách chủ động mà không phụ thuộc hoàn toàn vào dịch vụ serverless.
