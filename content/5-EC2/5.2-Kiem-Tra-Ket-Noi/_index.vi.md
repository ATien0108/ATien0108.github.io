---
title: "Kiểm tra kết nối"
date: 2025-07-09
weight: 2
chapter: false
pre: " <b> 5.2 </b> "
---

## Chuẩn bị môi trường

Truy cập quyền root để cài đặt các công cụ hệ thống.

      sudo su -

Cài đặt NVM (Node Version Manager).

      curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

Tải lại shell để sử dụng nvm

      . ~/.nvm/nvm.sh

<p align="center">
<img src="/images/5.2/5.2.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Cài đặt phiên bản Node.js mới nhất

      nvm install node

Kiểm tra phiên bản Node và npm đã được cài.

```bash
   node -v
```

```bash
   npm -v
```

<p align="center">
<img src="/images/5.2/5.2.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

## Cài Git và clone project

Cập nhật hệ thống và cài đặt Git.

```bash
   sudo yum update -y
```

```bash
   sudo yum install git -y
```

Kiểm tra phiên bản Git.

      git --version

<p align="center">
<img src="/images/5.2/5.2.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Tải mã nguồn ứng dụng từ GitHub.

      git clone https://github.com/DyyyPhatt/project-management.git

Điều hướng đến thư mục backend (server).

```bash
   ls
```

```bash
   cd project-management
```

```bash
   ls
```

```bash
   cd server
```

<p align="center">
<img src="/images/5.2/5.2.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

## Cài đặt và chạy server

Cài các gói npm cho backend.

      npm i

Chạy ứng dụng ở chế độ phát triển (development).

      npm run dev

<p align="center">
<img src="/images/5.2/5.2.5.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Tạo file .env và đặt port server là 80

      echo "PORT=80" > .env

Chạy lại server với file .env.

      npm run dev

<p align="center">
<img src="/images/5.2/5.2.6.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

## Cài và cấu hình PM2 để chạy nền

Cài đặt pm2 để quản lý tiến trình Node.js.

      npm i pm2 -g

Tạo file cấu hình PM2 (ecosystem.config.js).

      ls

<p align="center">
<img src="/images/5.2/5.2.7.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

      nano ecosystem.config.js

<p align="center">
<img src="/images/5.2/5.2.8.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Thiết lập PM2 tự khởi động khi máy chủ reboot.

      sudo env PATH=$PATH:$(which node) $(which pm2) startup systemd -u $USER --hp $(eval echo $USER)

<p align="center">
<img src="/images/5.2/5.2.9.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Khởi chạy server bằng PM2, kiểm tra trạng thái và giám sát.

```bash
   pm2 start ecosystem.config.js
```

```bash
   pm2 status
```

<p align="center">
<img src="/images/5.2/5.2.10.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

      pm2 monit

<p align="center">
<img src="/images/5.2/5.2.11.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Dừng và xóa toàn bộ tiến trình PM2 hiện tại.

```bash
   pm2 stop all
```

```bash
   pm2 delete all
```

<p align="center">
<img src="/images/5.2/5.2.12.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Khởi động lại server từ config.

      pm2 start ecosystem.config.js
