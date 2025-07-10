---
title: "Launch EC2 Instance"
date: 2025-07-09
weight: 1
chapter: false
pre: " <b> 5.1 </b> "
---

## Instance Configuration

1. Go to the **EC2 Dashboard**

   - Search for the **EC2** service

   - Select **EC2** from the search results

<p align="center">
<img src="/images/5.1/5.1.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

2. Launch a new Instance

   - Select **Instances** from the left-hand menu

   - Click **Launch instances**

<p align="center">
<img src="/images/5.1/5.1.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

3. Set the Instance Name

   - Under **Name and tags**, enter `pm_ec2-backend`

<p align="center">
<img src="/images/5.1/5.1.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

4. Choose Amazon Machine Image (AMI)

   - Select **Quick Start**

   - Choose **Amazon Linux 2**

   - Pick a suitable AMI version

<p align="center">
<img src="/images/5.1/5.1.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

5. Configure Instance Type and Key Pair

   - Choose an appropriate **Instance type**

   - Click **Create new key pair**

<p align="center">
<img src="/images/5.1/5.1.5.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

6. Create a new Key Pair

   - **Key pair name**: `pm-keypair`

   - **Key pair type**: Select **RSA**

   - **Private key format**: Select **.pem**

<p align="center">
<img src="/images/5.1/5.1.6.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Network Settings

7. Configure Network

   - **VPC**: Select the **PM** VPC

   - **Subnet**: Select **_Public Subnet 1_**

   - **Auto-assign public IP**: Select **_Enable_**

   - **Security Group**: Choose **Create Security Group**

   - **Security Group Name**: `pm_ec2-sg`

   - **Description**: `pm_ec2-sg`

   - Click **Launch instance**

<p align="center">
<img src="/images/5.1/5.1.7.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

8. Confirm the instance was launched successfully

<p align="center">
<img src="/images/5.1/5.1.8.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

#### Connect

Access the **EC2** service:

- Click **Instances**

- Select _**pm_ec2-backend**_

- Click **Connect**

<p align="center">
<img src="/images/5.1/5.1.connect1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

In the **Connect to instance** section:

- Choose **Connection Type**

- **Username**: _**ec2-user**_

- Click **Connect**

<p align="center">
<img src="/images/5.1/5.1.connect2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

✅ You have successfully connected!

<p align="center">
<img src="/images/5.1/5.1.connect3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>
