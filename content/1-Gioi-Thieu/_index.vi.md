---
title: "Giới thiệu"
date: 2025-07-07

weight: 1
chapter: false
pre: " <b> 1. </b> "
---

**Nội dung chính của đề tài:**

Ứng dụng **Project Management Dashboard** là một nền tảng web hiện đại, hỗ trợ người dùng tạo, phân công và theo dõi dự án theo thời gian thực. Giao diện trực quan, dễ sử dụng, tích hợp biểu đồ và bảng dữ liệu giúp nâng cao hiệu quả làm việc nhóm.

---

## Mục tiêu đề tài

- Quản lý dự án, nhiệm vụ, thành viên nhóm và tiến độ dự án.
- Phân quyền người dùng rõ ràng, bảo mật.
- Cập nhật trạng thái và dữ liệu theo thời gian thực.
- Hỗ trợ kéo – thả nhiệm vụ, hiển thị trực quan bằng biểu đồ.
- Triển khai linh hoạt trên môi trường đám mây AWS.

---

## Công nghệ sử dụng

### Frontend

- **Next.js:** Framework React hỗ trợ SSR/SSG, tăng tốc độ tải trang và tối ưu SEO.
- **Tailwind CSS:** Thư viện CSS tiện dụng cho giao diện responsive.
- **Material UI Data Grid:** Bảng dữ liệu có sorting, filtering, pagination.
- **Redux Toolkit + RTK Query:** Quản lý state và gọi API hiệu quả.
- **React DnD:** Kéo – thả nhiệm vụ.
- **Recharts:** Vẽ biểu đồ trực quan (cột, tròn, đường...).

### Backend

- **Node.js + Express:** Cung cấp API RESTful.
- **Typescript:** Cải thiện tính rõ ràng và an toàn khi lập trình.
- **Prisma ORM + PostgreSQL:** Giao tiếp với CSDL quan hệ, dễ bảo trì và tối ưu truy vấn.
- **PgAdmin, Postman:** Hỗ trợ quản lý và kiểm thử trong quá trình phát triển.

---

## Dịch vụ AWS tích hợp

- **Amazon Cognito:** Đăng nhập, xác thực người dùng, cấp JWT token.
- **Amazon EC2:** Máy chủ backend Node.js.
- **Amazon RDS (PostgreSQL):** Lưu trữ dữ liệu có quản lý.
- **Amazon S3:** Lưu ảnh, tệp đính kèm.
- **AWS Lambda:** Xử lý serverless các tác vụ nhỏ như gửi email, cập nhật tự động.
- **Amazon API Gateway:** Quản lý và bảo mật các API endpoint.

---

## Mô hình hệ thống tổng quan

Ứng dụng theo mô hình **Client – Server – Cloud** với ba tầng chính:

1. **Frontend (Next.js):** Người dùng tương tác qua giao diện dashboard. Gửi JWT token khi gọi API.
2. **Backend (Express trên EC2):** Xử lý logic nghiệp vụ, xác thực token, kết nối cơ sở dữ liệu.
3. **Cơ sở dữ liệu (RDS – PostgreSQL):** Lưu trữ thông tin dự án, người dùng, nhiệm vụ.

**Tích hợp mở rộng:**

- **S3:** Lưu trữ hình ảnh, tệp đính kèm.
- **Lambda:** Thực thi tự động khi có sự kiện.
- **API Gateway:** Quản lý các API endpoint nếu dùng kiến trúc serverless.

---

**Sơ đồ kiến trúc hệ thống:**  
Next.js → Cognito → EC2 (Express) → RDS (PostgreSQL)  
Tích hợp thêm: S3, Lambda, API Gateway.
