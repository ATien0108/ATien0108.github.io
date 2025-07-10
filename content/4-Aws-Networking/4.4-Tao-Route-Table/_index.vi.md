---
title: "Tạo Route Table"
date: 2025-07-09
weight: 4
chapter: false
pre: " <b> 4.4 </b> "
---

## Tổng quan

- Route Table là thành phần định tuyến lưu lượng mạng trong VPC

- Xác định đường đi cho các gói tin giữa các subnet và internet

- Cho phép kiểm soát luồng dữ liệu vào/ra VPC

---

## Các bước thực hiện

1. Truy cập **VPC**

   - Chọn **Route Tables** từ menu bên trái

   - Chọn vào **Create route table**

<p align="center">
<img src="/images/4.4/4.4.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Cấu hình Route Table

   - **Name**: Nhập `Route table-Public`

   - **VPC**: Chọn VPC **PM** (VPC ID sẽ tự động điền)

   - Chọn **Create route table**

<p align="center">
<img src="/images/4.4/4.4.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Xác nhận tạo Route Table thành công

<p align="center">
<img src="/images/4.4/4.4.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Cấu hình định tuyến

4. Thêm route cho Internet Gateway

   - Chọn **Actions**

   - Chọn **Edit routes**

5. Cấu hình route mới

   - Chọn **Add route**

   - **Destination**: Nhập `0.0.0.0/0` (đại diện cho internet)

   - **Target**: Chọn **Internet Gateway** và chọn IGW đã tạo

   - Chọn **Save changes**

<p align="center">
<img src="/images/4.4/4.4.5.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Cấu hình định tuyến

6. Thiết lập subnet associations

   - Chọn tab **Subnet associations**

   - Chọn **Edit subnet associations**

7. Chọn các public subnet

   - Mở rộng cột **Subnet ID** để xem chi tiết

   - Chọn public subnet đã tạo

   - Chọn **Save associations**

<p align="center">
<img src="/images/4.4/4.4.7.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

8. Xác nhận cấu hình subnet associations thành công

<p align="center">
<img src="/images/4.4/4.4.8.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Cấu hình định tuyến

9. Truy cập giao diện VPC

   - Chọn **Route Tables** từ menu bên trái

   - Chọn vào **Create route table**

10. Cấu hình Route Table

    - **Name**: Nhập `Route table-Private-1`

    - **VPC**: Chọn VPC **PM** (VPC ID sẽ tự động điền)

    - Chọn **Create route table**

<p align="center">
<img src="/images/4.4/4.4.10.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

11. Xác nhận tạo Route Table thành công

<p align="center">
<img src="/images/4.4/4.4.11.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

12. Tương tự tạo **oute table-Private-2**

<p align="center">
<img src="/images/4.4/4.4.12.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/4.4/4.4.12.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Liên kết với Subnet

13. Thiết lập subnet associations

    - Chọn tab **Subnet associations**

    - Chọn **Edit subnet associations**

14. Chọn các public subnet

    - Mở rộng cột **Subnet ID** để xem chi tiết

    - Chọn cả 2 private subnet đã tạo

    - Chọn **Save associations**

15. Xác nhận cấu hình subnet associations thành công

<p align="center">
<img src="/images/4.4/4.4.15.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/4.4/4.4.15.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>
