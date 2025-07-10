---
title: "Mô hình kiến trúc hệ thống"
date: 2025-07-07
weight: 4
chapter: false
pre: " <b> 1.4 </b> "
---

Hệ thống được thiết kế theo mô hình **Client – Server – Cloud**, đảm bảo các yếu tố linh hoạt, mở rộng, và bảo mật. Ứng dụng bao gồm ba tầng chính: **giao diện người dùng** (frontend), **xử lý nghiệp vụ** (backend), và **lưu trữ dữ liệu** (database) được triển khai trên nền tảng AWS.

---

## Luồng hoạt động tổng quát

### 🎯 **Frontend (Next.js)**

- Người dùng tương tác qua dashboard: tạo dự án, giao nhiệm vụ, quản lý thành viên.
- Hệ thống sử dụng **Redux Toolkit** để quản lý trạng thái và **RTK Query** để gọi API.
- Khi người dùng đăng nhập, frontend gửi thông tin xác thực đến **Cognito** và nhận về **JWT token**, sau đó sử dụng token này để gọi các API bảo mật.

### 🔐 **AWS Cognito**

- Quản lý đăng ký, đăng nhập, quên mật khẩu, xác thực hai bước (MFA).
- Trả về JWT token gồm **accessToken, idToken** và **refreshToken.**
- Tích hợp dễ dàng với backend Express để xác thực mỗi API request.

### ⚙️ **Backend (Node.js + Express trên EC2)**

- Nhận các request từ frontend kèm theo **JWT token**.
- Xác minh token với **AWS Cognito**.
- Xử lý logic nghiệp vụ: tạo/cập nhật dự án, quản lý công việc, người dùng, phân quyền,...
- Kết nối với cơ sở dữ liệu **PostgreSQL** thông qua **Prisma ORM**.

### 🗃️ **Database (PostgreSQL trên RDS)**

- Lưu trữ dữ liệu về người dùng, dự án, nhiệm vụ, nhóm làm việc.
- Prisma ORM giúp thực hiện các thao tác như truy vấn, insert, update, delete dữ liệu một cách hiệu quả và an toàn.
- Quản lý và giám sát dữ liệu qua **PgAdmin** trong quá trình phát triển.

---

## Tùy chọn mở rộng

- 🗂️ **S3:** Lưu trữ tệp đính kèm như tài liệu dự án, ảnh đại diện người dùng,... Dễ dàng kết nối từ frontend.
- ⚡ **Lambda:** Thực thi các tác vụ nhẹ như gửi email, xử lý sự kiện, cập nhật trạng thái khi nhiệm vụ hoàn thành. Không cần duy trì máy chủ.
- 🌐 **API Gateway:** Quản lý và bảo vệ các endpoint **RESTful** nếu backend chuyển sang mô hình serverless (kết hợp Lambda + API Gateway).

---

## Các sơ đồ hệ thống

### 🧩 **Sơ đồ kiến trúc tổng thể (AWS Architecture)**

<p align="center">
  <img src="/images/1.4/architecture.png" alt="Sơ đồ kiến trúc tổng thể" style="max-width:600px; width:100%; display:block; margin:auto;" />
</p>

- Minh họa các thành phần chính: **Next.js → Cognito → EC2 → RDS**, tích hợp với **S3, Lambda, API Gateway**.

### 🗂️ **Sơ đồ dữ liệu (Data Model)**

<p align="center">
  <img src="/images/1.4/datamodel.png" alt="Data model diagram" style="max-width:600px; width:100%; display:block; margin:auto;" />
</p>

- Thể hiện mối quan hệ giữa các bảng: **User, Project, Task, Team, Priority, Status,...**

### 🔐 **Sơ đồ xác thực Cognito**

- Diễn giải quy trình xác thực qua Cognito: **Đăng nhập → nhận token → sử dụng trong API → phân quyền backend**.

  **Saving User:**

    <p align="center">
    <img src="/images/1.4/saving-user.png" style="max-width:800px; width:100%; display:block; margin:auto;" />
  </p>

  **Fetching User:**

    <p align="center">
    <img src="/images/1.4/fetching-user.png" style="max-width:800px; width:100%; display:block; margin:auto;" />
  </p>

  **Securing API:**

    <p align="center">
    <img src="/images/1.4/securing-api.png" style="max-width:800px; width:100%; display:block; margin:auto;" />
  </p>
