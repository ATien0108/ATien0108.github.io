---
title: "Create Subnet"
date: 2025-07-09
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

## Overview

- A subnet is a smaller network segment within a VPC
- Allows distribution of resources across Availability Zones (AZ)
- Supports classification into public and private networks

---

## Steps to Follow

1. Go to the **VPC** service

   - Select **Subnets** from the left-hand menu
   - Click **Create subnet**

<p align="center">
<img src="/images/4.2/4.2.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Select a VPC

   - In the **Create subnet** screen
   - Choose the **PM** VPC created earlier

3. Configure the first subnet

   - **Subnet name**: Enter `Public Subnet 1`
   - **Availability Zone**: Choose **_ap-southeast-1a_**
   - **IPv4 CIDR block**: Enter `10.0.0.0/24`
   - Click **Create subnet**

<p align="center">
<img src="/images/4.2/4.2.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

4. Confirm the subnet was created successfully

<p align="center">
<img src="/images/4.2/4.2.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

### Create Additional Subnets

5. Repeat the process to create the following subnets:

   - **Private Subnet 1**

     - **CIDR block**: `10.0.1.0/24`
     - **AZ**: **_ap-southeast-1a_**

   - **Private Subnet 2**
     - **CIDR block**: `10.0.2.0/24`
     - **AZ**: **_ap-southeast-1b_**

<p align="center">
<img src="/images/4.2/4.2.5.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

**Note on Availability Zones:**  
AWS distinguishes between:

- **Availability Zone (AZ)**: Human-readable name (e.g., ap-southeast-1a)
- **AZ ID**: The actual identifier for the AZ  
  AWS maps AZ names to AZ IDs differently for each account to distribute resource allocation more evenly.

<p align="center">
<img src="/images/4.2/4.2.luu-y.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>
