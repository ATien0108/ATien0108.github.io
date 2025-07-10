---
title: "Tải Postman"
date: 2025-07-09
weight: 6
chapter: false
pre: " <b> 2.6 </b> "
---

## Tổng quan

Postman là công cụ hỗ trợ kiểm thử API phổ biến nhất hiện nay. Nó cho phép lập trình viên:

- Gửi request (GET, POST, PUT, DELETE, PATCH) đến server backend.

- Đính kèm header, body, token để kiểm tra xác thực.

- Quan sát trực tiếp phản hồi từ API.

- Lưu lại các tập request theo collection để dùng nhiều lần.

Trong đề tài này, Postman được dùng để:

- Kiểm tra hoạt động của các API do backend Express cung cấp.

- Gửi token xác thực từ Cognito để kiểm tra phân quyền.

- Thử nghiệm nhanh chức năng tạo dự án, nhiệm vụ, người dùng,… trước khi tích hợp với frontend.

---

## Nội dung

1. Truy cập trang chủ chính thức của Postman:
   https://www.postman.com/downloads/

2. Chọn đúng hệ điều hành và tải về:

   - Windows: file .exe

   - macOS: file .zip hoặc .dmg

   - Linux: file .tar.gz hoặc AppImage

3. Cài đặt như phần mềm thông thường. Sau khi mở Postman, bạn có thể đăng nhập tài khoản (hoặc chọn "Skip and take me to the app").

4. Giao diện chính của Postman bao gồm:

   - **Request URL**: nơi nhập endpoint API.

   - **Method**: chọn phương thức HTTP (GET, POST,…).

   - **Headers**: thêm thông tin như Authorization: Bearer [token].

   - **Body**: dùng với POST/PUT để gửi dữ liệu JSON.

5. Tạo Collection riêng cho dự án để lưu các request dùng nhiều lần (vd: Login, Get All Projects, Create Task,...)
