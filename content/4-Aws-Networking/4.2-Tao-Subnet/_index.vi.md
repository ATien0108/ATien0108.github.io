---
title: "Tạo Subnet"
date: 2025-07-09
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

## Tổng quan

- Subnet là phân đoạn mạng con trong VPC

- Cho phép phân phối tài nguyên theo vùng sẵn sàng (AZ)

- Hỗ trợ phân loại mạng public và private

---

## Các bước thực hiện

1. Truy cập **VPC**

   - Chọn **Subnets** từ menu bên trái

   - Chọn vào **Create subnet**

<p align="center">
<img src="/images/4.2/4.2.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Chọn VPC

   - Trong giao diện **Create subnet**

   - Chọn VPC **PM** đã tạo trước đó

3. Cấu hình Subnet đầu tiên

   - **Subnet name**: Nhập `Public Subnet 1`

   - **Availability Zone**: Chọn **_ap-southeast-1a_**

   - **IPv4 CIDR**: Nhập `10.0.0.0/24`

   - Chọn **Create subnet**

<p align="center">
<img src="/images/4.2/4.2.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

4. Xác nhận tạo subnet thành công

<p align="center">
<img src="/images/4.2/4.2.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Tạo các Subnet bổ sung

5. Lặp lại quy trình để tạo thêm các subnet sau:

   - **Private Subnet 1**

     - **CIDR**: `10.0.1.0/24`

     - **AZ**: **_ap-southeast-1a_**

   - **Private Subnet 2**

     - **CIDR**: `10.0.2.0/24`

     - **AZ**: **_ap-southeast-1b_**

<p align="center">
<img src="/images/4.2/4.2.5.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

**Lưu ý về Availability Zone** AWS sử dụng hai khái niệm:

- **Availability Zone (AZ)**: Tên hiển thị (ví dụ: ap-southeast-1a)

- **AZ ID**: Định danh thực tế của AZ AWS ánh xạ ngẫu nhiên AZ với AZ ID giữa các tài khoản để đảm bảo phân phối tài nguyên đồng đều.

<p align="center">
<img src="/images/4.2/4.2.luu-y.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>
