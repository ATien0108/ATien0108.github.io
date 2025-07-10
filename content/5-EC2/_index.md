---
title: "EC2"
date: 2025-07-09
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

## Overview

Amazon EC2 (Elastic Compute Cloud) is AWS’s virtual server service that allows you to run applications flexibly and on demand. In this project, EC2 is used to deploy the backend application.

The main steps include:

- **Launching an EC2 instance**: Select an operating system, configure hardware specs, create a key pair, and attach the instance to the appropriate VPC network.

- **Connecting and setting up the environment**: SSH into the instance, install Node.js, Git, and required libraries to run a Node.js backend.

- **Managing processes with PM2**: Run the server in the background and enable automatic restart upon system reboot.

Mastering EC2 operations empowers you to deploy applications independently without fully relying on serverless services.
