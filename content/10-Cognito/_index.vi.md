---
title: "Cognito"
date: 2025-07-09
weight: 10
chapter: false
pre: " <b> 10. </b> "
---

1. Truy cập **AWS Management Console**

- Tìm kiếm dịch vụ **Amazon Cognito**
- Chọn **Amazon Cognito** từ kết quả tìm kiếm

<p align="center">
<img src="/images/10/10.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Chọn **Create user pool**

<p align="center">
<img src="/images/10/10.2.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Ở **Configure sign-in experience**

  - Chọn **User name, Email**
  - Chọn **Allow users to sign in with a preferred user name và Make username case sensitive**
  - Chọn **Next**

    <p align="center">
  <img src="/images/10/10.2.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
  </p>

✅ Xác nhận thành công

<p align="center">
<img src="/images/10/10.2.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Cập nhật đoạn code

- Vào **User pool**
- Chọn **User pool** - **pbk6qc**

<p align="center">
<img src="/images/10/10.3.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Chọn tab **App clients**
- Ở **App client name**: **Project Management**
- Copy **Client ID**

<p align="center">
<img src="/images/10/10.3.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Dán **< Client ID >** vào file **.env.local** ở dòng: **NEXT_PUBLIC_COGNITO_USER_POOL_CLIENT_ID**

4. Truy cập **AWS Management Console**

- Tìm kiếm dịch vụ **AWS Amplify**
- Chọn **AWS Amplify** từ kết quả tìm kiếm

5. Chọn **View app - Project Management**

6. Chọn **Environment Variables**

<p align="center">
<img src="/images/10/10.6.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Chọn **Add new**
- **Variable**: **NEXT_PUBLIC_COGNITO_USER_POOL_ID**
- **Value**: là giá trị trong code **.env.local** ở dòng **NEXT_PUBLIC_COGNITO_USER_POOL_ID**
- **Variable**: **NEXT_PUBLIC_COGNITO_USER_POOL_CLIENT_ID**
- **Value**: là giá trị trong code **.env.local** ở dòng **NEXT_PUBLIC_COGNITO_USER_POOL_CLIENT_ID**
- Chọn **Save**

<p align="center">
<img src="/images/10/10.6.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

7. Truy cập **AWS Management Console**

- Tìm kiếm dịch vụ **Lambda**
- Chọn **Lambda** từ kết quả tìm kiếm

<p align="center">
<img src="/images/10/10.7.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

8. Chọn Create a function

<p align="center">
<img src="/images/10/10.8.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Chọn **Author from scratch**
- **Function name**: `pm_lambda-trigger`
- Chọn **Create function**

<p align="center">
<img src="/images/10/10.8.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/10/10.8.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

9. Chọn vào lambda vừa tạo **_pm_lambda-trigger_**

- Ở tab **Code**
- Nhập đoạn code:

```ts
import https from "node:https";

export const handler = async (event: any) => {
  const postData = JSON.stringify({
    username:
      event.request.userAttributes["preferred_username"] || event.userName,
    cognitoId: event.userName,
    profilePictureUrl: "i1.jpg",
    teamId: 1,
  });

  const options = {
    hostname: "<your-api-gateway-id>.execute-api.<region>.amazonaws.com",
    port: 443,
    path: "/create-user",
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      "Content-Length": Buffer.byteLength(postData),
    },
  };

  await new Promise((resolve, reject) => {
    const req = https.request(options, (res) => {
      res.setEncoding("utf8");
      let responseBody = "";

      res.on("data", (chunk) => {
        responseBody += chunk;
      });

      res.on("end", () => {
        console.log("Response from API:", responseBody);
        resolve(responseBody);
      });
    });

    req.on("error", (error) => {
      console.error("Error in HTTPS request:", error);
      reject(error);
    });

    req.write(postData);
    req.end();
  });

  return event;
};
```

- Chọn **Deploy**

<p align="center">
<img src="/images/10/10.9.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>

10. Vào **Amazon Cognito > User pools > pm-ProjectManagement-userpool**

- Ở tab **User pool properties**

<p align="center">
<img src="/images/10/10.10.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>

- Chọn **Add Lambda trigger**
  - **Trigger type**: _**Sign-up**_
  - **Sign-up**: _**Post confirmation trigger**_
  - **Assign Lambda function**: _**pm_lambda-trigger**_
  - Chọn **Create lambda trigger**

<p align="center">
<img src="/images/10/10.10.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>

<p align="center">
<img src="/images/10/10.10.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>

11. Vào **API Gateway > APis > pm_api-gateway (80okiqrybg) > Authorizers > Create authorizer**

<p align="center">
<img src="/images/10/10.11.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>

- **Authorizer name**: nhập `pm_api-gateway-authorizer`
- **Authorizer type**: chọn _**Cognito**_
- **Cognito user pool**: chọn _**pm-ProjectManagement-userpool**_
- **Token source**: **_Authorization_**
- Chọn **Create Authorizer**

<p align="center">
<img src="/images/10/10.11.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>

<p align="center">
<img src="/images/10/10.11.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>

12. Vào **EC2 > Instance > pm_ec2-backend > Connect**

- Ở EC2 Instance Connect
- Nhập lần lượt các lệnh:

  `sudo su -`

  `ls`

  `cd project-management/`

  `git pull`

  `cd server`

  `ls`

  `nano .env`

  `pm2 delete all`

  `pm2 start ecosystem.config.js`

  `pm2 monit`

<p align="center">
<img src="/images/10/10.12.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>

<p align="center">
<img src="/images/10/10.12.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>

<p align="center">
<img src="/images/10/10.12.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>

<p align="center">
<img src="/images/10/10.12.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>

<p align="center">
<img src="/images/10/10.12.5.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>
