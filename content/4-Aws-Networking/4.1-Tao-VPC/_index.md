---
title: "Create VPC"
date: 2025-07-09
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

## Objective

- Create a separate virtual network environment in AWS
- Define the IP address range for the VPC
- Configure basic DNS features

---

## Steps to Follow

1. Access the **AWS Management Console**

   - Search for the **VPC** service
   - Select **VPC** from the search results

<p align="center">
<img src="/images/4.1/4.1.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. In the **VPC Dashboard**

   - Select **Your VPCs** from the left menu
   - Click **Create VPC**

<p align="center">
<img src="/images/4.1/4.1.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Configure VPC parameters

   - **Resources**: Select **VPC only**
   - **Name tag**: Enter `PM`
   - **IPv4 CIDR**: Enter `10.0.0.0/16`

**Note on Tenancy**  
Keep the **Tenancy** option as **Default**. Switching to **Dedicated** may restrict the types of EC2 Instances supported in this VPC.

4. Confirm VPC creation

   - Click **Create VPC** to complete the process

<p align="center">
<img src="/images/4.1/4.1.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

5. Verify VPC status after creation

<p align="center">
<img src="/images/4.1/4.1.5.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

6. Enable DNS features for the VPC

   - Click **Edit VPC settings**
   - Go to the **DNS settings** tab
   - Enable **DNS hostnames** and **DNS resolution**
   - Save changes

<p align="center">
<img src="/images/4.1/4.1.6.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>
