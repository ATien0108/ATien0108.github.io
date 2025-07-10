---
title: "Tải PostgreSQL"
date: 2025-07-09
weight: 4
chapter: false
pre: " <b> 2.4 </b> "
---

## Tổng quan

**PostgreSQL** là một **hệ quản trị cơ sở dữ liệu quan hệ mã nguồn mở**, **mạnh mẽ** và **linh hoạt**. Trong đề tài này, **PostgreSQL** được sử dụng làm **hệ thống lưu trữ dữ liệu chính** cho **backend**, bao gồm thông tin **người dùng**, **dự án**, **nhiệm vụ**, **nhóm**, **phân quyền**,...

**Backend (Node.js + Express)** sẽ tương tác với **PostgreSQL** thông qua **Prisma ORM**, giúp **quản lý và truy vấn dữ liệu hiệu quả**.

**PostgreSQL** sẽ được **cài đặt và chạy cục bộ** trong quá trình **phát triển và thử nghiệm hệ thống**.

---

## Nội dung

1. Truy cập trang tải **PostgreSQL** chính thức:
   https://www.postgresql.org/download/

2. Chọn hệ điều hành tương ứng (Windows, macOS, Linux).

3. Với Windows/macOS, chọn tải về thông qua PostgreSQL Installer (EDB), sau đó chạy file .exe hoặc .pkg.

4. Trong quá trình cài đặt:

   - Chọn cài đặt thêm công cụ **PgAdmin** (nếu chưa có).

   - Thiết lập mật khẩu cho user mặc định postgres.

5. Hoàn tất quá trình cài đặt và kiểm tra **PostgreSQL** đã hoạt động bằng cách:

   - Mở **PgAdmin** hoặc **Terminal** và **dùng lệnh**: `title = "Write content"`
