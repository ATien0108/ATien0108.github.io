---
title: "Tạo VPC"
date: 2025-07-09
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

## Mục tiêu

- Tạo môi trường mạng ảo riêng biệt trong AWS

- Thiết lập không gian địa chỉ IP cho VPC

- Cấu hình các tính năng DNS cơ bản

---

## Các bước thực hiện

1. Truy cập **AWS Management Console**

   - Tìm kiếm dịch vụ **VPC**

   - Chọn **VPC** từ kết quả tìm kiếm

<p align="center">
<img src="/images/4.1/4.1.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Trong giao diện **VPC Dashboard**

   - Chọn **Your VPCs** từ menu bên trái

   - Chọn vào C**reate VPC**

<p align="center">
<img src="/images/4.1/4.1.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Cấu hình thông số VPC

   - **Resources**: Chọn **VPC only**

   - **Name tag**: Nhập `PM`

   - **IPv4 CIDR**: Nhập `10.0.0.0/16`

**Lưu ý về Tenancy** Giữ tùy chọn **Tenancy** ở chế độ mặc định (Default). Việc chuyển sang Dedicated có thể giới hạn các loại EC2 Instance được hỗ trợ trong VPC.

4. Xác nhận tạo VPC

   - Chọn **Create VPC** để hoàn tất quá trình

<p align="center">
<img src="/images/4.1/4.1.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

5. Kiểm tra trạng thái VPC sau khi tạo

<p align="center">
<img src="/images/4.1/4.1.5.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

6. Kích hoạt tính năng DNS cho VPC

   - Chọn **Edit VPC settings**

   - Mở tab **DNS settings**

   - Bật **DNS hostnames** và **DNS resolution**

   - Lưu thay đổi

<p align="center">
<img src="/images/4.1/4.1.6.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>
