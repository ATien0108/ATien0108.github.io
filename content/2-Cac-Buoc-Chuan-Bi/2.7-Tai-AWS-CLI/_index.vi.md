---
title: "Tải AWS CLI"
date: 2025-07-09
weight: 7
chapter: false
pre: " <b> 2.7 </b> "
---

## Tổng quan

AWS CLI (Command Line Interface) là công cụ dòng lệnh chính thức của Amazon Web Services, cho phép người dùng:

- Tương tác và quản lý tài nguyên AWS trực tiếp từ terminal.

- Triển khai dịch vụ EC2, RDS, S3, Cognito,... bằng lệnh thay vì thao tác thủ công trên giao diện web.

- Tích hợp với các quy trình DevOps, CI/CD, tự động hóa triển khai backend hoặc migrate dữ liệu.

Trong đề tài này, AWS CLI được sử dụng để:

- Kết nối và triển khai ứng dụng backend lên Amazon EC2.

- Cấu hình truy cập dịch vụ RDS, S3, Cognito.

- Quản lý các tài nguyên AWS qua lệnh hoặc script shell.

---

## Nội dung

1. Truy cập trang chính thức của AWS CLI:
   https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html

2. Chọn phiên bản phù hợp với hệ điều hành:

   - Windows: tải file .msi

   - macOS: dùng Homebrew hoặc file .pkg

   - Linux: sử dụng lệnh curl hoặc yum, apt tùy distro

3. Cài đặt theo hướng dẫn. Sau khi cài thành công, mở Terminal (hoặc CMD) và kiểm tra: `aws --version`

   - ✅ Nếu hiển thị như: _aws-cli/2.15.x Python/3.x.x_

   - => Bạn đã cài thành công AWS CLI phiên bản 2.

4. Đăng nhập AWS CLI với tài khoản cá nhân: `aws configure`

   - CLI sẽ yêu cầu nhập: **AWS Access Key ID** và **AWS Secret Access Key**

   - Default region (ví dụ: us-east-1)

   - Default output format (gợi ý: json)

   - Bạn có thể tạo **Access Key** trong trang **AWS IAM > Security credentials**.
