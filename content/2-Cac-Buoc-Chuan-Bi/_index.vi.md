---
title: "Các bước chuẩn bị"
date: 2025-07-03
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

## Tổng quan

Trước khi chạy ứng dụng **Project Management Dashboard**, bạn cần chuẩn bị đầy đủ công cụ, thư viện và cấu hình môi trường cần thiết cho cả frontend và backend. Mục này hướng dẫn từng bước cài đặt và cấu hình trên máy tính cá nhân.

---

## Danh sách từng bước

### ✅ **2.1 – Clone mã nguồn**

- Sử dụng lệnh `git clone` để tải toàn bộ mã nguồn từ GitHub.
- Kho lưu trữ: 👉 https://github.com/DyyyPhatt/project-management

### ✅ **2.2 – Cài đặt Node.js**

- Cần thiết để chạy frontend (Next.js) và backend (Express).
- Tự động cài đặt kèm công cụ quản lý thư viện `npm`.

### ✅ **2.3 – Cài đặt Visual Studio Code**

- IDE được khuyến nghị để viết và quản lý mã nguồn.
- Cài thêm các tiện ích mở rộng như Markdown, JavaScript/TypeScript, Prisma,...

### ✅ **2.4 – Cài đặt PostgreSQL**

- Hệ quản trị cơ sở dữ liệu quan hệ chính của hệ thống.
- Lưu thông tin người dùng, dự án, nhiệm vụ, nhóm, phân quyền,...

### ✅ **2.5 – Cài đặt PgAdmin**

- Công cụ giao diện đồ họa để quản lý cơ sở dữ liệu PostgreSQL.
- Hỗ trợ xem bảng, dữ liệu mẫu, viết truy vấn SQL.

### ✅ **2.6 – Cài đặt Postman**

- Công cụ kiểm thử các API (GET, POST, PUT, DELETE).
- Cho phép gửi token xác thực để kiểm tra quyền truy cập API.

### ✅ **2.7 – Cài đặt AWS CLI**

- Công cụ dòng lệnh để tương tác với các dịch vụ AWS như EC2, RDS, S3, Cognito.
- Dùng để triển khai backend và quản lý tài nguyên trên AWS.

### ✅ **2.8 – Cài đặt thư viện cần thiết**

- Cài thư viện frontend:
  - Next.js, Tailwind CSS, MUI Data Grid, Redux Toolkit, RTK Query, React DnD, Recharts, Gantt Chart,...
- Cài thư viện backend:
  - Express.js, Prisma ORM và các công cụ liên quan.

---

👉 Sau khi hoàn tất các bước trên, bạn có thể tiếp tục với phần **cấu hình dự án, thiết lập cơ sở dữ liệu và triển khai hệ thống**.
