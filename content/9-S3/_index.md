---
title: "S3"
date: 2025-07-09
weight: 9
chapter: false
pre: " <b> 9. </b> "
---

1. Access **AWS Management Console**

- Search for **Amazon S3**
- Select **Amazon S3** from the search results

<p align="center">
<img src="/images/9/9.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Click **Create bucket**

<p align="center">
<img src="/images/9/9.2.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- **Bucket name**: `pm-s3-images-ws`

<p align="center">
<img src="/images/9/9.2.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Uncheck **Block all public access**
- Check **I acknowledge that the current settings might result in this bucket and the objects within becoming public**

<p align="center">
<img src="/images/9/9.2.3.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Click **Create bucket**

✅ Confirm bucket creation success

<p align="center">
<img src="/images/9/9.2.4.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Select the `pm-s3-images-ws` bucket

<p align="center">
<img src="/images/9/9.3.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Upload all images from the `public` folder inside the `client` directory
- **Files and folders**: 29 Total, 16.3 MB

<p align="center">
<img src="/images/9/9.3.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Click **Upload**
- Click **Close**

<p align="center">
<img src="/images/9/9.3.3.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

4. Configure access permissions

- Go to the **Permissions** tab

<p align="center">
<img src="/images/9/9.4.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Click **Edit** in the **Bucket policy** section
- Paste the following JSON:

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

- Click **Save changes**

<p align="center">
<img src="/images/9/9.4.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

5. Update the code in **next.config.ts**

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

6. Update all **< Image >** components with the new S3 URL paths

<p align="center">
<img src="/images/9/9.6.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

7. Push code to GitHub to trigger website redeployment
