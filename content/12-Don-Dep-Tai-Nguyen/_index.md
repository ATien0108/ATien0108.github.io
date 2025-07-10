---
title: "Resource Cleanup"
date: 2025-07-09
weight: 12
chapter: false
pre: " <b> 12. </b> "
---

### Delete Cognito

- **Step 1: Access Amazon Cognito**

  - Open [Amazon Cognito Console](https://console.aws.amazon.com/cognito/)
  - Select **User Pools** from the left-hand navigation

- **Step 2: Select the User Pool to delete**
  - Find and click the **User Pool** you want to delete

<p align="center">
<img src="/images/12/12.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- **Step 3: Delete**
  - Click the **Delete user pool** button
  - Confirm by entering the **name of the User Pool**
  - Click **Delete** to finish

<p align="center">
<img src="/images/12/12.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

### Delete Lambda

- **Step 1: Access AWS Lambda Console**
  - Open [AWS Lambda Console](https://console.aws.amazon.com/lambda/)
  - From the Functions list, select the Lambda you want to delete

<p align="center">
<img src="/images/12/12.3.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- **Step 2: Delete**
  - Click **Actions > Delete**
  - Confirm in the prompt

<p align="center">
<img src="/images/12/12.4.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

### Delete S3

- **Step 1: Access Amazon S3**

  - Open [Amazon S3 Console](https://s3.console.aws.amazon.com/s3/)
  - From the bucket list, choose the bucket you want to delete

- **Step 2: Empty the bucket**
  - Click **Empty** at the top right
  - Confirm to delete all objects inside the bucket

<p align="center">
<img src="/images/12/12.5.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- **Step 3: Delete the bucket**
  - After the bucket is empty, click **Delete**
  - Enter the exact name of the bucket to confirm
  - Click **Delete bucket** to finish

<p align="center">
<img src="/images/12/12.6.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/12/12.7.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

### Delete API Gateway

- **Step 1: Access Amazon API Gateway**

  - Open [API Gateway Console](https://console.aws.amazon.com/apigateway/)
  - Select **APIs** from the left-hand navigation

- **Step 2: Select the API to delete**

  - Find the API you want to delete (HTTP, REST, or WebSocket)
  - Click the API name to open details

- **Step 3: Delete**
  - Click **Actions > Delete**
  - Confirm by entering the API name (if required)
  - Click **Delete** to finish

<p align="center">
<img src="/images/12/12.8.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/12/12.9.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

### Delete AWS Amplify

- **Step 1: Access AWS Amplify Console**

  - Open [AWS Amplify Console](https://console.aws.amazon.com/amplify/home)
  - From the application list, choose the app you want to delete

- **Step 2: Open app settings**

  - In the app details page, select the **App settings** tab
  - Click **General** to view general settings

- **Step 3: Delete the app**
  - Scroll down and click **Delete app**
  - Enter the app name to confirm
  - Click **Delete** to complete

<p align="center">
<img src="/images/12/12.10.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/12/12.11.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

### Delete RDS

- **Step 1: Access Amazon RDS Console**

  - Open [Amazon RDS Console](https://console.aws.amazon.com/rds/)
  - In the navigation pane, select **Databases**

- **Step 2: Choose the database instance to delete**

  - Select the instance you want to delete from the list

- **Step 3: Delete**

  - Click **Actions > Delete**
  - In the confirmation dialog:
    - Choose/confirm options:
      - “Create final snapshot” if you want to back up before deletion (or uncheck if not needed)
      - “Delete automated backups” if you want to remove all old backups
    - Enter **delete me** to confirm

<p align="center">
<img src="/images/12/12.12.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- **Step 4: Monitor deletion process**
  - Deletion may take a few minutes
  - Check status in the **Databases** list (status changes to `deleting`, then disappears)

<p align="center">
<img src="/images/12/12.13.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/12/12.14.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

### Delete EC2

- **Step 1: Access EC2 Console**

  - Open [Amazon EC2 Console](https://console.aws.amazon.com/ec2/)
  - In the left-hand navigation pane, select **Instances**

- **Step 2: Select the EC2 instance to delete**

  - Locate and select the EC2 instance you want to delete

- **Step 3: Stop and terminate instance**

  - Click **Instance state > Terminate instance**
  - Confirm in the dialog that appears

<p align="center">
<img src="/images/12/12.15.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- **Step 4: Monitor status**
  - Instance status changes to `shutting-down`, then to `terminated`
  - You will no longer have access to the instance

<p align="center">
<img src="/images/12/12.16.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/12/12.17.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

### Delete Key Pair

- **Step 1: Access EC2 Console**

  - Open [Amazon EC2 Console](https://console.aws.amazon.com/ec2/)
  - From the left menu, choose **Key Pairs** (under **Network & Security**)

- **Step 2: Select the Key Pair to delete**

  - Find the unused key pair
  - Tick the checkbox next to its name

- **Step 3: Delete Key Pair**
  - Click **Actions > Delete key pair**
  - Confirm in the prompt

<p align="center">
<img src="/images/12/12.18.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

### Delete VPC

- **Step 1: Access VPC Console**

  - Open [Amazon VPC Console](https://console.aws.amazon.com/vpc/)
  - From the navigation pane, select **Your VPCs**

- **Step 2: Review related resources**

  - Before deleting a VPC, you must delete all dependent resources:
    - Subnets
    - Route Tables
    - Internet Gateways
    - NAT Gateways
    - Custom Security Groups
    - Network ACLs
    - Elastic IPs (if associated)
    - Endpoints, VPC Peering, VPN Connections
    - Load Balancers, EC2, RDS... in the VPC

- **Step 3: Delete the VPC**
  - Select the VPC from the list
  - Click **Actions > Delete VPC**
  - Confirm in the dialog

<p align="center">
<img src="/images/12/12.19.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/12/12.20.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

### Delete Subnet

- **Step 1: Access VPC Console**

  - Open [Amazon VPC Console](https://console.aws.amazon.com/vpc/)
  - From the navigation pane, select **Subnets**

- **Step 2: Select the subnet to delete**

  - Locate the subnet within the VPC
  - Tick to select the subnet

- **Step 3: Delete subnet**
  - Click **Actions > Delete subnet**
  - Confirm in the dialog

<p align="center">
<img src="/images/12/12.21.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

<p align="center">
<img src="/images/12/12.22.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>
