---
title: "Tải PgAdmin"
date: 2025-07-09
weight: 5
chapter: false
pre: " <b> 2.5 </b> "
---

## Tổng quan

PgAdmin là công cụ quản trị cơ sở dữ liệu PostgreSQL thông qua giao diện đồ họa (GUI), giúp người phát triển dễ dàng:

- Tạo và quản lý cơ sở dữ liệu.

- Truy vấn SQL trực tiếp.

- Theo dõi cấu trúc bảng, quan hệ và dữ liệu thực tế.

Trong dự án này, PgAdmin đóng vai trò là công cụ hỗ trợ quan sát và thao tác dữ liệu trong quá trình phát triển, đặc biệt hữu ích khi kết hợp với Prisma ORM và seed data.

---

## Nội dung

1. Truy cập trang tải chính thức: https://www.pgadmin.org/download/

2. Chọn phiên bản phù hợp với hệ điều hành đang sử dụng (Windows/macOS/Linux).

3. Tải về và tiến hành cài đặt như các phần mềm thông thường.

4. Sau khi cài đặt:

   - **Mở PgAdmin 4** từ menu hệ thống.

   - Ở lần đầu mở, hệ thống yêu cầu tạo mật khẩu cho giao diện → nhập và ghi nhớ.

   - Nhấn **Add New Server** để kết nối với **PostgreSQL local**:

   - **Name**: localhost

   - **Host name / address**: localhost

   - **Port**: 5432

   - **Username**: postgres

   - **Password**: (mật khẩu bạn đặt khi cài PostgreSQL, ví dụ: 1234)

5. Sau khi kết nối thành công, bạn có thể:

   - **Tạo database mới** (ví dụ: project_dashboard)

   - Quan sát bảng, dữ liệu mẫu (seed data)

   - Chạy **truy vấn SQL** trực tiếp trong tab **Query Tool**
