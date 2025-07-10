---
title: "Dịch vụ AWS sử dụng"
date: 2025-07-07
weight: 3
chapter: false
pre: " <b> 1.3 </b> "
---

## Amazon Cognito

<p align="center">
  <img src="/images/1.3/cognito.png" alt="Amazon Cognito" style="max-width:160px; width:100%; display:block; margin:auto;" />
</p>

- Xử lý đăng ký, đăng nhập và xác thực hai bước (MFA).
- Cấp JWT token để phân quyền và truy cập API an toàn.
- Tích hợp tốt với frontend (Next.js) và backend (Express) thông qua SDK hoặc REST API.

---

## Amazon EC2

<p align="center">
  <img src="/images/1.3/ec2.png" alt="Amazon EC2" style="max-width:160px; width:100%; display:block; margin:auto;" />
</p>

- Triển khai backend Node.js như một máy chủ thật.
- Tùy chỉnh cấu hình RAM, CPU, hệ điều hành.
- Hỗ trợ triển khai bằng Git, CI/CD hoặc SSH trực tiếp.

---

## Amazon RDS (PostgreSQL)

<p align="center">
  <img src="/images/1.3/rds.png" alt="Amazon RDS" style="max-width:160px; width:100%; display:block; margin:auto;" />
</p>

- Cung cấp cơ sở dữ liệu được quản lý hoàn toàn (auto backup, restore, patching).
- Cho phép backend (EC2) kết nối nội bộ, bảo mật tốt.
- Dễ giám sát hiệu năng qua CloudWatch.

---

## Amazon S3

<p align="center">
  <img src="/images/1.3/s3.png" alt="Amazon S3" style="max-width:160px; width:100%; display:block; margin:auto;" />
</p>

- Lưu hình ảnh người dùng, file tài liệu đính kèm.
- Cho phép frontend tải lên hoặc tải xuống theo từng user hoặc group.
- Dễ tích hợp với frontend thông qua pre-signed URL.

---

## AWS Lambda

<p align="center">
  <img src="/images/1.3/lambda.png" alt="AWS Lambda" style="max-width:160px; width:100%; display:block; margin:auto;" />
</p>

- Xử lý các tác vụ nhỏ như gửi email, đồng bộ dữ liệu mà không cần server riêng.
- Có thể chạy theo event trigger từ S3, DynamoDB, API Gateway,...

---

## Amazon API Gateway

<p align="center">
  <img src="/images/1.3/api.png" alt="Amazon API Gateway" style="max-width:160px; width:100%; display:block; margin:auto;" />
</p>

- Tạo và bảo mật các endpoint backend.
- Tích hợp tốt với Lambda hoặc backend Express nếu chia thành microservices.
- Hỗ trợ kiểm soát truy cập (usage plans, API keys, throttling).

## AWS Amplify

<p align="center">
  <img src="/images/1.3/ampilify.png" alt="Amazon API Gateway" style="max-width:160px; width:100%; display:block; margin:auto;" />
</p>

- Triển khai frontend (Next.js) dễ dàng với CI/CD tích hợp GitHub.
- Tích hợp với các dịch vụ khác như Cognito, S3, API Gateway nhanh chóng.
- Hỗ trợ hosting SPA/SSR và backend-as-a-service (GraphQL, REST API).
