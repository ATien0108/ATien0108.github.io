---
title: "Create Internet Gateway"
date: 2025-07-09
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

## Overview

- An Internet Gateway (IGW) is a VPC component that enables internet connectivity
- Acts as a bridge between your VPC and the internet
- Supports bidirectional communication for resources inside the VPC

---

## Steps to Follow

1. Go to the **VPC** service

   - Select **Internet Gateways** from the left-hand menu
   - Click on **Create internet gateway**

<p align="center">
<img src="/images/4.3/4.3.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Configure the Internet Gateway

   - In the **Name tag** field, enter `Internet Gateway`
   - Click **Create internet gateway**

<p align="center">
<img src="/images/4.3/4.3.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Confirm the Internet Gateway was created successfully

<p align="center">
<img src="/images/4.3/4.3.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Attach to VPC

4. Attach the Internet Gateway to your VPC

   - Click **Actions**
   - Choose **Attach to VPC**
   - Select the **PM** VPC from the dropdown (VPC ID will auto-fill)
   - Click **Attach internet gateway**

<p align="center">
<img src="/images/4.3/4.3.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Confirm Status

5. Once attached:

   - The **State** of the Internet Gateway will change to **Attached**
   - The IGW is now ready to route internet traffic for your VPC

<p align="center">
<img src="/images/4.3/4.3.5.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>
