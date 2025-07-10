---
title: "AWS NETWORKING"
date: 2025-07-03
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

## 🛰️ Tổng quan về AWS Networking

Hệ thống **mạng ảo (AWS Networking)** trong AWS được xây dựng xoay quanh **VPC (Virtual Private Cloud)** – một mạng riêng biệt, cách ly logic trong môi trường đám mây. Việc cấu hình các thành phần mạng bao gồm **VPC**, **Subnet**, **Internet Gateway**, và **Route Table** là bước nền tảng để triển khai các dịch vụ như EC2, RDS,... hoạt động một cách an toàn và linh hoạt.

---

### **VPC – Virtual Private Cloud**

- Là môi trường mạng riêng biệt trong AWS.
- Cho phép người dùng định nghĩa không gian địa chỉ IP, cấu hình DNS, kiểm soát truy cập và định tuyến lưu lượng.
- Là lớp mạng gốc để chứa các subnet, gateway, security group,...

---

### **Subnet – Mạng con**

- Subnet chia VPC thành các đoạn mạng nhỏ hơn, phân bố theo **Availability Zone (AZ)**.
- Có thể được cấu hình là **Public** (truy cập internet) hoặc **Private** (chỉ truy cập nội bộ).
- Cho phép tổ chức tài nguyên (EC2, RDS,...) một cách logic và an toàn.

---

### **Internet Gateway – Cổng kết nối internet**

- Là cầu nối giữa VPC và internet.
- Cần được gắn vào VPC để các subnet public có thể truy cập hoặc nhận lưu lượng từ bên ngoài.
- Hỗ trợ giao tiếp 2 chiều cho các tài nguyên như EC2 đặt trong public subnet.

---

### **Route Table – Bảng định tuyến**

- Quy định hướng đi của lưu lượng mạng trong VPC.
- Cho phép ánh xạ lưu lượng đến **Internet Gateway**, subnet khác hoặc VPN.
- Mỗi subnet cần được liên kết (associate) với một Route Table phù hợp với chức năng (public/private).

---

### ✅ Tổng kết

| Thành phần           | Vai trò chính                                                                    |
| -------------------- | -------------------------------------------------------------------------------- |
| **VPC**              | Mạng riêng biệt chứa toàn bộ tài nguyên mạng                                     |
| **Subnet**           | Chia nhỏ không gian mạng, định nghĩa phạm vi hoạt động của tài nguyên            |
| **Internet Gateway** | Kết nối mạng công cộng, cho phép truy cập internet cho subnet                    |
| **Route Table**      | Xác định tuyến đường cho lưu lượng mạng, ánh xạ subnet với Gateway hoặc VPC khác |
