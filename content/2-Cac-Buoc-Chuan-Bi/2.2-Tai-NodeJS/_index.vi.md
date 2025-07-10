---
title: "Tải Node.js"
date: 2025-07-09
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

## Tổng quan

**Node.js** là một môi trường chạy JavaScript phía máy chủ, được sử dụng để xây dựng backend của hệ thống trong đề tài này. Dự án backend sử dụng Node.js kết hợp với Express để xử lý các API và kết nối cơ sở dữ liệu.

Cùng với Node.js, hệ thống còn cần **npm** (Node Package Manager) – công cụ giúp quản lý và cài đặt các thư viện cần thiết cho cả frontend và backend.

Cả frontend (Next.js) và backend (Express.js) trong dự án đều yêu cầu cài đặt Node.js để chạy và phát triển.

---

## Nội dung

1. Truy cập trang tải chính thức của Node.js: https://nodejs.org/en

2. Chọn bản ổn định **(LTS – Long Term Support)** phù hợp với hệ điều hành:

   Windows: `.msi` installer

   macOS: `.pkg` installer

   Linux: chọn phiên bản tương ứng với bản phân phối

3. Tải xuống và cài đặt như phần mềm thông thường (Next → Next → Install...).

4. Kiểm tra cài đặt bằng cách mở terminal hoặc Command Prompt và nhập:
   ```bash
   node -v
   npm -v
   ```

👉 Nếu kết quả hiển thị phiên bản như **_v18.x.x (Node)_** và **_9.x.x (npm)_** → nghĩa là bạn đã _cài đặt thành công_.
