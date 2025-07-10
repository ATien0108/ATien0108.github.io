---
title: "S3"
date: 2025-07-09
weight: 9
chapter: false
pre: " <b> 9. </b> "
---

1. Truy cập **AWS Management Console**

- Tìm kiếm dịch vụ **Amazon S3**
- Chọn **Amazon S3** từ kết quả tìm kiếm

<p align="center">
<img src="/images/9/9.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Chọn **Create bucket**

<p align="center">
<img src="/images/9/9.2.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- **Bucket name**: `pm-s3-images-ws`

<p align="center">
<img src="/images/9/9.2.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Bỏ chọn **Block all public access**
- Tích chọn **I acknowledge that the current settings might result in this bucket and the objects within becoming public**

<p align="center">
<img src="/images/9/9.2.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Chọn **Create bucket**

✅ Xác nhận tạo bucket thành công

<p align="center">
<img src="/images/9/9.2.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Chọn bucket `pm-s3-images-ws`

<p align="center">
<img src="/images/9/9.3.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Upload toàn bộ ảnh trong thư mục `public` của thư mục `client`
- **Files and folders**: 29 Total, 16.3 MB

<p align="center">
<img src="/images/9/9.3.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Chọn **Upload**
- Chọn **Close**

<p align="center">
<img src="/images/9/9.3.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

4. Cấu hình quyền truy cập

- Chọn tab **Permissions**

<p align="center">
<img src="/images/9/9.4.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Chọn **Edit** tại mục **Bucket policy**
- Dán đoạn mã JSON sau:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::pm-s3-images-ws/*"
    }
  ]
}
```

- Chọn **Save changes**

<p align="center">
<img src="/images/9/9.4.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

5. Cập nhật đoạn code file **next.config.ts**

```ts
import type { NextConfig } from "next";

const nextConfig: NextConfig = {
  images: {
    remotePatterns: [
      {
        protocol: "https",
        hostname: "pm-s3-images-ws.s3.ap-southeast-1.amazonaws.com",
        port: "",
        pathname: "/**",
      },
    ],
  },
};

export default nextConfig;
```

<p align="center">
<img src="/images/9/9.5.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

6. Cập nhật lại tất cả các thẻ **< Image >** với đường dẫn mới

<p align="center">
<img src="/images/9/9.6.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

7. Thực hiện Push code lên Github để Deploy lại Website
