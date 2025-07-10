---
title: "Install PostgreSQL"
date: 2025-07-09
weight: 4
chapter: false
pre: " <b> 2.4 </b> "
---

## Overview

**PostgreSQL** is an **open-source relational database management system** that is both **powerful** and **flexible**. In this project, **PostgreSQL** serves as the **primary data storage system** for the **backend**, handling information such as **users**, **projects**, **tasks**, **teams**, **permissions**, and more.

The **backend (Node.js + Express)** communicates with **PostgreSQL** using **Prisma ORM**, enabling **efficient data management and querying**.

**PostgreSQL** will be **installed and run locally** during the **development and testing phases**.

---

## Instructions

1. Visit the official **PostgreSQL** download page:  
   https://www.postgresql.org/download/

2. Select your corresponding operating system (Windows, macOS, or Linux).

3. For Windows/macOS, download using the PostgreSQL Installer (EDB), then run the `.exe` or `.pkg` file.

4. During the installation process:

   - Choose to install **PgAdmin** (if not already available).

   - Set a password for the default `postgres` user.

5. After installation, verify that **PostgreSQL** is working by:

   - Opening **PgAdmin** or using the **Terminal** with the following command:

     ```bash
     psql -U postgres
     ```
