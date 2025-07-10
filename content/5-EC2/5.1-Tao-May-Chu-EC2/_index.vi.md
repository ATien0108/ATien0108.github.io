---
title: "Tạo VPC"
date: 2025-07-09
weight: 1
chapter: false
pre: " <b> 5.1 </b> "
---

## Cấu hình Instance

1. Truy cập **EC2 Dashboard**

   - Tìm kiếm dịch vụ **EC2**

   - Chọn **EC2** từ kết quả tìm kiếm

<p align="center">
<img src="/images/5.1/5.1.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Khởi tạo Instance mới

   - Chọn **Instances** từ menu bên trái

   - Chọn **Launch instances** instances

<p align="center">
<img src="/images/5.1/5.1.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Đặt tên Instance

   - Tại **Name and tags**, nhập `pm_ec2-backend`

<p align="center">
<img src="/images/5.1/5.1.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

4. Chọn Amazon Machine Image (AMI)

   - Chọn **Quick Start**

   - Chọn **Amazon Linux 2**

   - Chọn phiên bản AMI phù hợp

<p align="center">
<img src="/images/5.1/5.1.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

5. Cấu hình Instance và Key Pair

   - Chọn **Instance** type phù hợp

   - Chọn **Create new key pair**

<p align="center">
<img src="/images/5.1/5.1.5.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

6. Tạo Key Pair mới

   - **Key pair name**: Nhập `pm-keypair`

   - **Key pair type**: Chọn **RSA**

   - **Private key format**: Chọn **.pem**

<p align="center">
<img src="/images/5.1/5.1.6.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Cấu hình Network

7. Thiết lập Network Settings

   - **VPC**: Chọn VPC **PM**

   - **Subnet**: Chọn **_Public Subnet 1_**

   - **Auto-assign public IP**: Chọn **_Enable_**

   - **Security Group**: Chọn vào mục **Create Security Group**

   - **Security Group Name**: **_pm_ec2-sg_**

   - **Description**: **_pm_ec2-sg_**

   - Chọn **Launch instance**

<p align="center">
<img src="/images/5.1/5.1.7.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

8. Xác nhận khởi tạo thành công

<p align="center">
<img src="/images/5.1/5.1.8.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Connect

Truy cập vào **EC2**

- Chọn **Instances**

- Chọn _**pm_ec2-backend**_

- Chọn **Connect**

<p align="center">
<img src="/images/5.1/5.1.connect1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Trong mục Connect to instance

- Chọn **Connection Type**

- **Username**: _**ec2-user**_

- Chọn **Connect**

<p align="center">
<img src="/images/5.1/5.1.connect2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

=> Kết nối thành công

<p align="center">
<img src="/images/5.1/5.1.connect3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>
