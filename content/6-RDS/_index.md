---
title: "RDS"
date: 2025-07-09
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

1. Access the **Amazon RDS Console**:

<p align="center">
<img src="/images/6/6.1.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Click **Databases**
- Click **Create database**

2. Select database creation method:

- Choose **Standard create**

3. Configure the database engine:

- Select **PostgreSQL**

<p align="center">
<img src="/images/6/6.3.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

4. Set up the template:

- Choose **Free-tier**

<p align="center">
<img src="/images/6/6.4.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

5. Continue with detailed configuration:

- **DB instance identifier**: `pm-rds`
- **Master username**: `postgres`
- Switch to **Self managed**

6. Enter credentials:

- **Master password**: your own password (e.g., `hellomyfriend1234`)
- **Confirm password**

<p align="center">
<img src="/images/6/6.6.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

7. Storage – Storage autoscaling

- Uncheck **Enable storage autoscaling**

<p align="center">
<img src="/images/6/6.7.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

8. Connectivity

- **Virtual Private Cloud (VPC)**: Select _**PM**_
- **DB subnet group**: Select _**Create new DB Subnet Group**_
- **Public Access**: Select _**No**_
- **VPC Security Group**: Select _**Create new**_
- **New VPC security group name**: _**pm_rd-sg**_
- **Availability Zone**: _**ap-southeast-1a**_

9. Monitoring: Uncheck _**Enable Performance Insights**_

<p align="center">
<img src="/images/6/6.9.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

10. Additional configuration

- **Initial database name**: `projectmanagement`
- **DB parameter group**: _**default.postgres17**_
- Backup: uncheck **Enable automated backups**
- Encryption: uncheck **Enable encryption**

<p align="center">
<img src="/images/6/6.10.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

11. Click **Create database**

<p align="center">
<img src="/images/6/6.11.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

## Security Group Configuration

12. Edit **Inbound rules** – Security Group

- Go to **EC2**
- Select **Security Groups**

<p align="center">
<img src="/images/6/6.12.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Choose **pm_rd-sg**
- Click **Edit inbound rules**

<p align="center">
<img src="/images/6/6.12.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Click **Add rule**
- **Type**: _**PostgreSQL**_
- **Source**: _**Custom**_
- Select **pm_ec2-sg**
- Click **Save rules**

<p align="center">
<img src="/images/6/6.12.3.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

13. Edit **Outbound rules** – Security Group

- Go to **EC2**
- Select **Security Groups**
- Select **pm_ec2-sg**
- Click **Edit outbound rules**

<p align="center">
<img src="/images/6/6.13.1.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

- Click **Add rule**
  - **Type**: _**PostgreSQL**_
  - **Source**: _**Custom**_
  - Select **pm_rd-sg**
  - Click **Save rules**

<p align="center">
<img src="/images/6/6.13.2.png" style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

## Connect from EC2

14. Access the EC2 instance via Connect

- Run: `pm2 delete all`
- Run: `nano .env`
- Paste the following into the `.env` file, then save:

```dotenv
DATABASE_URL="postgresql://postgres:<RDS password>@<RDS endpoint>:5432/<DB Name>?schema=public"
```
