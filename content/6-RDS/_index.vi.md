---
title: "RDS"
date: 2025-07-09
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

1.  Truy cập vào **Amazon RDS Console**:

<p align="center">
<img src="/images/6/6.1.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Chọn **Databases**

- Chọn **Create database**

2.  Chọn phương thức tạo database:

- Chọn **Standard create**

3.  Cấu hình Engine database:

- Chọn **PostgreSQL**

<p align="center">
<img src="/images/6/6.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

4.  Cấu hình Template:

- Chọn **Free-tier**

<p align="center">
<img src="/images/6/6.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

5.  Tiếp theo, thực hiện cài đặt chi tiết:

- **DB instance identifier**: nhập `pm-rds`

- **Master username**: nhập `postgres`

- Chọn sang **Self managed**

6.  Tiếp tục:

- **Master password**: nhập tùy ý của bạn (Ví dụ: hellomyfriend1234)

- **Confirm password**: nhập lại password một lần nữa

<p align="center">
<img src="/images/6/6.6.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

7.  Storage - Storage autoscaling

- Tick bỏ chọn **Enable storage autoscaling**

<p align="center">
<img src="/images/6/6.7.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

8.  Connectivity

- **Virtual Private Cloud (VPC)**: Chọn VPC _**PM**_

- **DB subnet group**: Chọn _**Create new DB Subnet Group**_

- **Public Access**: Chọn _**No**_

- **VPC Security Group**: Chọn _**Create new**_

- **New VPC security group name**: _**pm_rd-sg**_

- **Availability Zone**: _**ap-southeast-1a**_

9.  Monitoring: bỏ chọn _**Enable Performance Insights**_

<p align="center">
<img src="/images/6/6.9.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

10. Additional configuration

- **Initial database name**: nhập `projectmanagement`

- **DB parameter group**: chọn _**default.postgres17**_

- Backup bỏ chọn **Enable automated backups**

- Encryption bỏ chọn **Enable encryption**

<p align="center">
<img src="/images/6/6.10.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

11. Create Dateabse

<p align="center">
<img src="/images/6/6.11.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

12. _Edit inbound rules_ - Security Group

- Truy cập vào **EC2**

- Chọn **Security Group**

<p align="center">
<img src="/images/6/6.12.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Chọn **pm_rd-sg**

- Chọn **Edit inbound rules**

<p align="center">
<img src="/images/6/6.12.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Chọn **Add rule**

- **Type**: _**PostgreSQL**_

- **Source**: _**Customer**_

- Chọn **pm_ec2-sg**

- **Save rules**

<p align="center">
<img src="/images/6/6.12.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

13. _Edit outbound rules_ - Security Group

- Truy cập vào **EC2**

- Chọn **Security Group**

- Chọn **pm_ec2-sg**

- Chọn **Edit outbound rules**

<p align="center">
<img src="/images/6/6.13.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Chọn **Add rule**

  - **Type**: _**PostgreSQL**_

  - **Source**: _**Customer**_

  - Chọn **pm_rd-sg**

  - **Save rules**

<p align="center">
<img src="/images/6/6.13.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

14. Truy cập vào EC2 Instance Connect

- `pm2 delete all`

- `nano .env`

- Dán đoạn code vào .env sau đó save

  - `DATABASE_URL="postgresql://postgres:<mật khẩu RDS>@<endpoint_RDS>:5432/<DB Name>?schema=public"`

<p align="center">
<img src="/images/6/6.14.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Sinh các tệp Prisma Client từ schema.

  - `npx prisma generate`

<p align="center">
<img src="/images/6/6.14.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Tạo và chạy migration để khởi tạo database (init là tên migration).

  - `npx prisma migrate dev --name init`

<p align="center">
<img src="/images/6/6.14.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Chạy lệnh seed để thêm dữ liệu mẫu vào DB.

  - `npm run seed`

<p align="center">
<img src="/images/6/6.14.5.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Khởi động lại ứng dụng với môi trường và DB đã hoàn chỉnh.

  - `pm2 start ecosystem.config.js`

<p align="center">
<img src="/images/6/6.14.6.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/6/6.14.7.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>
