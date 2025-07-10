---
title: "Install PgAdmin"
date: 2025-07-09
weight: 5
chapter: false
pre: " <b> 2.5 </b> "
---

## Overview

**PgAdmin** is a graphical user interface (GUI) tool for managing **PostgreSQL** databases. It allows developers to:

- Create and manage databases.
- Run SQL queries directly.
- View table structures, relationships, and actual data.

In this project, **PgAdmin** is used as a support tool for monitoring and interacting with the data during development. It is especially helpful when working with **Prisma ORM** and **seed data**.

---

## Instructions

1. Visit the official download page:  
   https://www.pgadmin.org/download/

2. Choose the version that matches your operating system (Windows/macOS/Linux).

3. Download and install it as you would any typical software.

4. After installation:

   - **Open PgAdmin 4** from your system menu.

   - On first launch, you'll be prompted to set a master password for the GUI → enter and remember it.

   - Click **Add New Server** to connect to your **local PostgreSQL**:

     - **Name**: localhost
     - **Host name / address**: localhost
     - **Port**: 5432
     - **Username**: postgres
     - **Password**: (the password you set during PostgreSQL installation, e.g., `1234`)

5. Once connected successfully, you can:

   - **Create a new database** (e.g., `project_dashboard`)
   - Browse tables and view **seed data**
   - Run **SQL queries** directly in the **Query Tool** tab
