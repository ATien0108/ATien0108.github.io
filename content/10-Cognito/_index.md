---
title: "Cognito"
date: 2025-07-09
weight: 10
chapter: false
pre: " <b> 10. </b> "
---

1. Access **AWS Management Console**

- Search for **Amazon Cognito** service
- Select **Amazon Cognito** from the search results

<p align="center">
<img src="/images/10/10.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Click **Create user pool**

<p align="center">
<img src="/images/10/10.2.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- In **Configure sign-in experience**:
  - Select **User name, Email**
  - Check **Allow users to sign in with a preferred user name** and **Make username case sensitive**
  - Click **Next**

<p align="center">
<img src="/images/10/10.2.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

✅ Successfully created

<p align="center">
<img src="/images/10/10.2.3.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Update the code

- Go to **User pool**
- Select **User pool - pbk6qc**

<p align="center">
<img src="/images/10/10.3.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Go to the **App clients** tab
- In **App client name**: **Project Management**
- Copy the **Client ID**

<p align="center">
<img src="/images/10/10.3.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Paste the **Client ID** into the `.env.local` file at: **NEXT_PUBLIC_COGNITO_USER_POOL_CLIENT_ID**

4. Access **AWS Management Console**

- Search for **AWS Amplify**
- Select **AWS Amplify** from the search results

5. Click **View app - Project Management**

6. Click **Environment Variables**

<p align="center">
<img src="/images/10/10.6.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- ChClick ọn **Add new**
- **Variable**: **NEXT_PUBLIC_COGNITO_USER_POOL_ID**
- **Value**: from **.env.local** code **NEXT_PUBLIC_COGNITO_USER_POOL_ID**
- **Variable**: **NEXT_PUBLIC_COGNITO_USER_POOL_CLIENT_ID**
- **Value**: from **.env.local** code **NEXT_PUBLIC_COGNITO_USER_POOL_CLIENT_ID**
- Click **Save**

<p align="center">
<img src="/images/10/10.6.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

7. Access **AWS Management Console**

- Search for **Lambda**
- Select **Lambda** from the results

<p align="center">
<img src="/images/10/10.7.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

8. Click Create a function

<p align="center">
<img src="/images/10/10.8.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Choose **Author from scratch**
- **Function name**: `pm_lambda-trigger`
- Click **Create function**

<p align="center">
<img src="/images/10/10.8.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/10/10.8.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

9. Select the created Lambda function: **_pm_lambda-trigger_**

- In the **Code** tab
- Paste the following code:

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

- Click **Deploy**

<p align="center">
<img src="/images/10/10.9.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>

10. Go to **Amazon Cognito > User pools > pm-ProjectManagement-userpool**

- In the **User pool properties** tab

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

- **Authorizer name**: `pm_api-gateway-authorizer`
- **Authorizer type**: _**Cognito**_
- **Cognito user pool**: _**pm-ProjectManagement-userpool**_
- **Token source**: **_Authorization_**
- **Create Authorizer**

<p align="center">
<img src="/images/10/10.11.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>

<p align="center">
<img src="/images/10/10.11.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto/>
</p>

12. Go to **EC2 > Instance > pm_ec2-backend > Connect**

- In EC2 Instance Connect
- Run the following commands:

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
