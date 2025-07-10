---
title: "Create Route Table"
date: 2025-07-09
weight: 4
chapter: false
pre: " <b> 4.4 </b> "
---

## Overview

- A Route Table defines how network traffic is directed within a VPC
- It determines the paths that packets take between subnets and the internet
- Enables control over inbound/outbound traffic in your VPC

---

## Steps to Follow

1. Access the **VPC** service

   - Select **Route Tables** from the left-hand menu
   - Click on **Create route table**

<p align="center">
<img src="/images/4.4/4.4.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Configure the Route Table

   - **Name**: Enter `Route table-Public`
   - **VPC**: Choose the **PM** VPC (VPC ID will auto-fill)
   - Click **Create route table**

<p align="center">
<img src="/images/4.4/4.4.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Confirm the route table was created successfully

<p align="center">
<img src="/images/4.4/4.4.3.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Configure Routing

4. Add route for Internet Gateway

   - Click **Actions**
   - Select **Edit routes**

5. Add new route

   - Click **Add route**
   - **Destination**: Enter `0.0.0.0/0` (represents internet)
   - **Target**: Select **Internet Gateway** and choose the previously created IGW
   - Click **Save changes**

<p align="center">
<img src="/images/4.4/4.4.5.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Associate with Subnet

6. Go to **Subnet associations** tab

   - Click **Edit subnet associations**

7. Select public subnets

   - Expand the **Subnet ID** column to view details
   - Select the public subnet created earlier
   - Click **Save associations**

<p align="center">
<img src="/images/4.4/4.4.7.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

8. Confirm successful subnet association

<p align="center">
<img src="/images/4.4/4.4.8.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Create Private Route Tables

9. Return to the VPC dashboard

   - Select **Route Tables**
   - Click **Create route table**

10. Configure the Route Table

- **Name**: Enter `Route table-Private-1`
- **VPC**: Select **PM** VPC
- Click **Create route table**

<p align="center">
<img src="/images/4.4/4.4.10.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

11. Confirm successful creation

<p align="center">
<img src="/images/4.4/4.4.11.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

12. Similarly, create another route table named `Route table-Private-2`

<p align="center">
<img src="/images/4.4/4.4.12.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/4.4/4.4.12.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Associate with Private Subnets

13. Set up subnet associations

- Go to **Subnet associations** tab
- Click **Edit subnet associations**

14. Select both private subnets

- Expand **Subnet ID** to view details
- Select both previously created private subnets
- Click **Save associations**

15. Confirm successful subnet association

<p align="center">
<img src="/images/4.4/4.4.15.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/4.4/4.4.15.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>
