---
title: "API Gateway"
date: 2025-07-09
weight: 8
chapter: false
pre: " <b> 8. </b> "
---

1. Truy cập AWS Management Console

- Tìm kiếm dịch vụ **API Gateway**
- Chọn **API Gateway** từ kết quả tìm kiếm

<p align="center">
<img src="/images/8/8.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Tìm đến mục REST API

- Chọn **Build**

<p align="center">
<img src="/images/8/8.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Create REST API

- Chọn **New API**
- **API name**: `pm_api-gateway`
- Chọn **Create API**

<p align="center">
<img src="/images/8/8.3.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

✅ Xác nhận tạo REST API thành công

<p align="center">
<img src="/images/8/8.3.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

4. Tìm đến mục Resource

5. Chọn Create Resource

- Mở **Proxy Resource**
- **Resource name**: `{proxy+}`
- Chọn **CORS (Cross Origin Resource Sharing)**
- Chọn **Create Resource**

<p align="center">
<img src="/images/8/8.5.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

✅ Xác nhận tạo Resource thành công

<p align="center">
<img src="/images/8/8.5.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

6. Trong Methods của Resource

- Chọn **ANY**

<p align="center">
<img src="/images/8/8.6.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Chọn **Edit integration**
  - **Integration Type**: `HTTP`
  - Mở **HTTP proxy integration**
  - **HTTP Method**: `ANY`
  - **Endpoint URL**: `<Public IPv4 Address>/{proxy}`
  - **Content handling**: `Passthrough`
- Chọn **Save**

<p align="center">
<img src="/images/8/8.6.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

✅ Xác nhận chỉnh sửa thành công

<p align="center">
<img src="/images/8/8.6.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

7. Chọn Deploy API

- **Stage**: _New stage_
- **Stage name**: `prod`
- Chọn **Deploy**

<p align="center">
<img src="/images/8/8.7.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

8. Kiểm tra API

<p align="center">
<img src="/images/8/8.8.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

9. Truy cập AWS Management Console

- Tìm kiếm dịch vụ **AWS Amplify**
- Chọn **AWS Amplify** từ kết quả tìm kiếm

10. Chọn **View app - Project Management**

<p align="center">
<img src="/images/8/8.10.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

11. Chọn Environment Variables

- Chọn **Manage Variables**

<p align="center">
<img src="/images/8/8.11.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Cập nhật **Value** của biến **NEXT_PUBLIC_API_BASE_URL**
- Chọn **Save**

<p align="center">
<img src="/images/8/8.11.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

12. Chọn Overview

- Chọn **master**
- Chọn **Redeploy this version**

<p align="center">
<img src="/images/8/8.12.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>
