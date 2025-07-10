---
title: "AWS NETWORKING"
date: 2025-07-03
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

## 🛰️ Overview of AWS Networking

The **AWS Networking** system is built around **VPC (Virtual Private Cloud)** – a logically isolated virtual network in the AWS cloud. Setting up core networking components such as **VPC**, **Subnets**, **Internet Gateway**, and **Route Tables** is foundational for securely deploying services like EC2, RDS, and more.

---

### **VPC – Virtual Private Cloud**

- Acts as a private network within AWS.
- Allows you to define IP address ranges, DNS settings, access control, and routing rules.
- Serves as the base layer containing subnets, gateways, and security resources.

---

### **Subnet – Network Segmentation**

- Divides the VPC into smaller address spaces, distributed across **Availability Zones (AZs)**.
- Can be configured as **Public** (internet-facing) or **Private** (internal only).
- Enables logical and secure placement of resources like EC2 and RDS.

---

### **Internet Gateway (IGW)**

- A gateway that connects the VPC to the internet.
- Must be attached to a VPC to allow public subnets to communicate externally.
- Supports two-way communication for internet-accessible resources.

---

### **Route Table**

- Defines how network traffic is routed within a VPC.
- Maps traffic to destinations such as an **Internet Gateway**, other subnets, or VPN connections.
- Each subnet must be associated with a route table that aligns with its function (public/private).

---

### ✅ Summary

| Component            | Description                                                                |
| -------------------- | -------------------------------------------------------------------------- |
| **VPC**              | The isolated network containing all other networking resources             |
| **Subnet**           | Segments the VPC and scopes the visibility and access of resources         |
| **Internet Gateway** | Connects the VPC to the public internet for outbound/inbound communication |
| **Route Table**      | Controls traffic flow by defining routing paths within and outside the VPC |
