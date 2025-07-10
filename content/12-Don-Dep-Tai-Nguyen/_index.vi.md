---
title: "Dọn dẹp tài nguyên"
date: 2025-07-09
weight: 12
chapter: false
pre: " <b> 12. </b> "
---

### Xóa Cognito

- **Bước 1: Truy cập Amazon Cognito**

  - Mở [Amazon Cognito Console](https://console.aws.amazon.com/cognito/)
  - Chọn **User Pools** từ thanh điều hướng bên trái

- **Bước 2: Chọn User Pool cần xóa**
  - Tìm và nhấn vào **User Pool** bạn muốn xóa

<p align="center">
<img src="/images/12/12.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- **Bước 3: Thực hiện xóa**
  - Nhấn nút **Delete user pool**
  - Xác nhận bằng cách nhập **tên của User Pool**
  - Nhấn **Delete** để hoàn tất

<p align="center">
<img src="/images/12/12.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

### Xóa Lambda

- **Bước 1: Truy cập AWS Lambda Console**
  - Mở [AWS Lambda Console](https://console.aws.amazon.com/lambda/)
  - Trong danh sách chức năng (Functions), chọn Lambda bạn muốn xóa

<p align="center">
<img src="/images/12/12.3.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- **Bước 2: Thực hiện xóa**
  - Nhấn nút **Actions > Delete**
  - Xác nhận xóa trong hộp thoại hiện ra

<p align="center">
<img src="/images/12/12.4.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

### Xóa S3

- **Bước 1: Truy cập Amazon S3**

  - Mở [Amazon S3 Console](https://s3.console.aws.amazon.com/s3/)
  - Trong danh sách bucket, chọn bucket bạn muốn xóa

- **Bước 2: Empty (làm trống) bucket**
  - Nhấn vào **Empty** ở góc trên bên phải
  - Xác nhận để xóa toàn bộ đối tượng bên trong bucket

<p align="center">
<img src="/images/12/12.5.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- **Bước 3: Delete (xóa) bucket**
  - Sau khi bucket đã trống, nhấn nút **Delete**
  - Nhập chính xác tên bucket để xác nhận
  - Nhấn **Delete bucket** để hoàn tất

<p align="center">
<img src="/images/12/12.6.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/12/12.7.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

### Xóa API Gateway

- **Bước 1: Truy cập Amazon API Gateway**

  - Mở [API Gateway Console](https://console.aws.amazon.com/apigateway/)
  - Chọn **APIs** từ thanh điều hướng bên trái

- **Bước 2: Chọn API cần xóa**

  - Tìm đến API bạn muốn xóa (HTTP, REST hoặc WebSocket API)
  - Nhấn vào tên API để mở chi tiết

- **Bước 3: Thực hiện xóa**
  - Nhấn nút **Actions > Delete**
  - Xác nhận bằng cách nhập tên API (nếu được yêu cầu)
  - Nhấn **Delete** để hoàn tất

<p align="center">
<img src="/images/12/12.8.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>

<p align="center">
<img src="/images/12/12.9.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>

### Xóa AWS Amplify

- **Bước 1: Truy cập AWS Amplify Console**

  - Mở [AWS Amplify Console](https://console.aws.amazon.com/amplify/home)
  - Trong danh sách ứng dụng, chọn app bạn muốn xóa

- **Bước 2: Mở phần cài đặt của ứng dụng**

  - Trong trang chi tiết ứng dụng, chọn tab **App settings**
  - Nhấn **General** để vào cài đặt chung

- **Bước 3: Xóa ứng dụng**
  - Kéo xuống cuối trang, nhấn nút **Delete app**
  - Nhập tên ứng dụng để xác nhận
  - Nhấn **Delete** để hoàn tất

<p align="center">
<img src="/images/12/12.10.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>

<p align="center">
<img src="/images/12/12.11.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>

### Xóa RDS

- **Bước 1: Truy cập Amazon RDS Console**

  - Mở [Amazon RDS Console](https://console.aws.amazon.com/rds/)
  - Trong thanh điều hướng, chọn **Databases**

- **Bước 2: Chọn database instance cần xóa**

  - Chọn instance bạn muốn xóa từ danh sách

- **Bước 3: Thực hiện xóa**

  - Nhấn nút **Actions > Delete**
  - Trong hộp thoại xác nhận:
    - **Chọn/xác nhận các tuỳ chọn**:
      - “Create final snapshot” nếu muốn backup trước khi xóa (hoặc bỏ chọn nếu không cần)
      - “Delete automated backups” nếu muốn xóa toàn bộ backup cũ
    - Nhập **delete me** để xác nhận

<p align="center">
<img src="/images/12/12.12.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>

- **Bước 4: Theo dõi quá trình xóa**
  - Quá trình xóa có thể mất vài phút
  - Kiểm tra trạng thái trong bảng **Databases** (status sẽ chuyển sang `deleting`, sau đó biến mất)

<p align="center">
<img src="/images/12/12.13.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>

<p align="center">
<img src="/images/12/12.14.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>

### Xóa EC2

- **Bước 1: Truy cập EC2 Console**

  - Mở [Amazon EC2 Console](https://console.aws.amazon.com/ec2/)
  - Trong thanh điều hướng bên trái, chọn **Instances**

- **Bước 2: Chọn EC2 instance cần xóa**

  - Tìm và chọn EC2 instance bạn muốn xóa

- **Bước 3: Dừng và xóa instance**

  - Nhấn **Instance state > Terminate instance**
  - Xác nhận trong hộp thoại hiện ra để xóa

<p align="center">
<img src="/images/12/12.15.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>

- **Bước 4: Theo dõi trạng thái**
  - Trạng thái instance sẽ chuyển thành `shutting-down`, sau đó là `terminated`
  - Sau khi bị terminated, bạn sẽ không còn truy cập được vào instance

<p align="center">
<img src="/images/12/12.16.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>

<p align="center">
<img src="/images/12/12.17.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>

### Xóa Key Pair

- **Bước 1: Truy cập EC2 Console**

  - Mở [Amazon EC2 Console](https://console.aws.amazon.com/ec2/)
  - Trong thanh điều hướng bên trái, chọn **Key Pairs** (thuộc mục **Network & Security**)

- **Bước 2: Chọn Key Pair cần xóa**

  - Tìm đến key pair không còn sử dụng
  - Tick vào checkbox bên cạnh tên key

- **Bước 3: Xóa Key Pair**
  - Nhấn **Actions > Delete key pair**
  - Xác nhận trong hộp thoại hiện ra để hoàn tất xóa

<p align="center">
<img src="/images/12/12.18.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>

### Xóa VPC

- **Bước 1: Truy cập VPC Console**

  - Mở [Amazon VPC Console](https://console.aws.amazon.com/vpc/)
  - Trong thanh điều hướng bên trái, chọn **Your VPCs**

- **Bước 2: Kiểm tra tài nguyên liên quan**

  - Trước khi xóa VPC, bạn **phải xóa tất cả tài nguyên phụ thuộc**, bao gồm:
    - Subnets
    - Route Tables
    - Internet Gateways
    - NAT Gateways
    - Security Groups tùy chỉnh
    - Network ACLs
    - Elastic IPs (nếu có gán)
    - Endpoints, VPC Peering, VPN Connections
    - Load Balancers, EC2, RDS... trong VPC đó

- **Bước 3: Xóa VPC**
  - Chọn VPC muốn xóa trong danh sách
  - Nhấn **Actions > Delete VPC**
  - Xác nhận trong hộp thoại hiện ra

<p align="center">
<img src="/images/12/12.19.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>

<p align="center">
<img src="/images/12/12.20.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>

### Xóa Subnet

- **Bước 1: Truy cập VPC Console**

  - Mở [Amazon VPC Console](https://console.aws.amazon.com/vpc/)
  - Trong thanh điều hướng bên trái, chọn **Subnets**

- **Bước 2: Chọn subnet cần xóa**

  - Tìm subnet thuộc VPC bạn muốn dọn dẹp
  - Tick chọn subnet cần xóa

- **Bước 3: Xóa subnet**
  - Nhấn **Actions > Delete subnet**
  - Xác nhận trong hộp thoại hiện ra để hoàn tất

<p align="center">
<img src="/images/12/12.21.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>

<p align="center">
<img src="/images/12/12.22.png"  style="max-width:800px; width:100%; height:auto; display:block"; margin:auto/>
</p>
