---
title: "AWS Services Used"
date: 2025-07-07
weight: 3
chapter: false
pre: " <b> 1.3 </b> "
---

## Amazon Cognito

<p align="center">
  <img src="/images/1.3/cognito.png" alt="Amazon Cognito" style="max-width:160px; width:100%; display:block; margin:auto;" />
</p>

- Handles user sign-up, sign-in, and multi-factor authentication (MFA).
- Issues JWT tokens for secure API access and role-based authorization.
- Easily integrates with frontend (Next.js) and backend (Express) via SDK or REST API.

---

## Amazon EC2

<p align="center">
  <img src="/images/1.3/ec2.png" alt="Amazon EC2" style="max-width:160px; width:100%; display:block; margin:auto;" />
</p>

- Deploys the Node.js backend as a virtual server.
- Customizable RAM, CPU, and operating system configurations.
- Supports deployment via Git, CI/CD pipelines, or direct SSH access.

---

## Amazon RDS (PostgreSQL)

<p align="center">
  <img src="/images/1.3/rds.png" alt="Amazon RDS" style="max-width:160px; width:100%; display:block; margin:auto;" />
</p>

- Provides a fully managed database (automatic backups, restore, and patching).
- Enables secure internal connections from backend services (e.g., EC2).
- Easily monitorable via CloudWatch.

---

## Amazon S3

<p align="center">
  <img src="/images/1.3/s3.png" alt="Amazon S3" style="max-width:160px; width:100%; display:block; margin:auto;" />
</p>

- Stores user images and attached document files.
- Allows frontend upload/download operations based on user or group.
- Easy integration via pre-signed URLs.

---

## AWS Lambda

<p align="center">
  <img src="/images/1.3/lambda.png" alt="AWS Lambda" style="max-width:160px; width:100%; display:block; margin:auto;" />
</p>

- Handles small tasks like sending emails or syncing data without a dedicated server.
- Can be triggered by events from S3, DynamoDB, API Gateway, etc.

---

## Amazon API Gateway

<p align="center">
  <img src="/images/1.3/api.png" alt="Amazon API Gateway" style="max-width:160px; width:100%; display:block; margin:auto;" />
</p>

- Creates and secures backend endpoints.
- Easily integrates with Lambda or Express-based backends in a microservices architecture.
- Supports access control via usage plans, API keys, and throttling.

## AWS Amplify

<p align="center"> <img src="/images/1.3/ampilify.png" alt="AWS Amplify" style="max-width:160px; width:100%; display:block; margin:auto;" /> </p>

- Easily deploy frontend (Next.js) applications with GitHub-integrated CI/CD.
- Quickly integrate with other AWS services such as Cognito, S3, and API Gateway.
- Supports hosting for SPA/SSR and backend-as-a-service (GraphQL, REST API).
