---
title: "Tạo Internet Gateway"
date: 2025-07-09
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

## Tổng quan

- Internet Gateway (IGW) là thành phần VPC cho phép kết nối internet

- Cung cấp điểm kết nối giữa VPC và internet

- Hỗ trợ giao tiếp hai chiều cho các tài nguyên trong VPC

---

## Các bước thực hiện

1. Truy cập **VPC**

   - Chọn **Internet Gateways** từ menu bên trái

   - Chọn vào **Create internet gateway**

<p align="center">
<img src="/images/4.3/4.3.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Cấu hình Internet Gateway

   - Tại **Name tag**, nhập `Internet Gateway`

   - Chọn **Create internet gateway**

<p align="center">
<img src="/images/4.3/4.3.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Xác nhận tạo Internet Gateway thành công

<p align="center">
<img src="/images/4.3/4.3.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Kết nối với VPC

4. Gắn Internet Gateway vào VPC

   - Chọn **Actions**

   - Chọn **Attach to VPC**

   - Chọn VPC **PM** từ danh sách (VPC ID sẽ tự động điền)

   - Chọn **Attach internet gateway**

<p align="center">
<img src="/images/4.3/4.3.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Xác nhận trạng thái

5. Sau khi gắn thành công:

   - **State** của Internet Gateway sẽ chuyển sang **Attached**

   - IGW đã sẵn sàng định tuyến lưu lượng internet cho VPC

<p align="center">
<img src="/images/4.3/4.3.5.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>
