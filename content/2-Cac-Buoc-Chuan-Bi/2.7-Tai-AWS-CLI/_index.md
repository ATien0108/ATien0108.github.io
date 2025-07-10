---
title: "Install AWS CLI"
date: 2025-07-09
weight: 7
chapter: false
pre: " <b> 2.7 </b> "
---

## Overview

AWS CLI (Command Line Interface) is the official command-line tool provided by Amazon Web Services. It allows users to:

- Interact with and manage AWS resources directly from the terminal.
- Deploy services such as EC2, RDS, S3, Cognito, etc., using commands instead of manually navigating the AWS web console.
- Integrate with DevOps, CI/CD processes, and automate backend deployment or data migration.

In this project, AWS CLI is used to:

- Connect to and deploy the backend application to Amazon EC2.
- Configure access to services such as RDS, S3, and Cognito.
- Manage AWS resources through shell scripts or terminal commands.

---

## Instructions

1. Visit the official AWS CLI download page:  
   👉 https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html

2. Choose the appropriate version based on your operating system:

   - Windows: download the `.msi` installer
   - macOS: use Homebrew or the `.pkg` file
   - Linux: use `curl`, `yum`, or `apt` depending on your distro

3. Install following the official instructions. Once installed, open Terminal (or CMD) and check the version:

   ```bash
   aws --version
   ```

   - ✅ If the output looks like: aws-cli/2.15.x Python/3.x.x

   - => You have successfully installed AWS CLI version 2.

4. Log in to your AWS account via CLI by running: `aws configure`

   - The CLI will prompt for: **AWS Access Key ID** and **AWS Secret Access Key**

   - Default region (e.g., us-east-1)

   - Default output format (recommended: json)

   - You can create **Access Keys** in the **AWS IAM > Security credentials section**.
