---
title: "API Gateway"
date: 2025-07-09
weight: 8
chapter: false
pre: " <b> 8. </b> "
---

1. Access AWS Management Console

- Search for **API Gateway**
- Select **API Gateway** from the search results

<p align="center">
<img src="/images/8/8.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Navigate to the REST API section

- Click **Build**

<p align="center">
<img src="/images/8/8.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Create a REST API

- Select **New API**
- **API name**: `pm_api-gateway`
- Click **Create API**

<p align="center">
<img src="/images/8/8.3.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

✅ Confirm that the REST API was created successfully

<p align="center">
<img src="/images/8/8.3.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

4. Navigate to the **Resources** section

5. Click **Create Resource**

- Enable **Proxy Resource**
- **Resource name**: `{proxy+}`
- Check **CORS (Cross-Origin Resource Sharing)**
- Click **Create Resource**

<p align="center">
<img src="/images/8/8.5.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

✅ Confirm that the resource was created successfully

<p align="center">
<img src="/images/8/8.5.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

6. In the Resource Methods

- Choose **ANY**

<p align="center">
<img src="/images/8/8.6.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Click **Edit integration**
  - **Integration Type**: `HTTP`
  - Enable **HTTP proxy integration**
  - **HTTP Method**: `ANY`
  - **Endpoint URL**: `<Public IPv4 Address>/{proxy}`
  - **Content handling**: `Passthrough`
- Click **Save**

<p align="center">
<img src="/images/8/8.6.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

✅ Confirm the integration was updated successfully

<p align="center">
<img src="/images/8/8.6.3.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

7. Deploy the API

- **Stage**: _New stage_
- **Stage name**: `prod`
- Click **Deploy**

<p align="center">
<img src="/images/8/8.7.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

8. Test the API

<p align="center">
<img src="/images/8/8.8.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

9. Access AWS Management Console

- Search for **AWS Amplify**
- Select **AWS Amplify** from the search results

10. Click **View app - Project Management**

<p align="center">
<img src="/images/8/8.10.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

11. Open Environment Variables

- Click **Manage Variables**

<p align="center">
<img src="/images/8/8.11.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Update the **Value** of the variable **NEXT_PUBLIC_API_BASE_URL**
- Click **Save**

<p align="center">
<img src="/images/8/8.11.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

12. Go to **Overview**

- Select **master**
- Click **Redeploy this version**

<p align="center">
<img src="/images/8/8.12.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>
