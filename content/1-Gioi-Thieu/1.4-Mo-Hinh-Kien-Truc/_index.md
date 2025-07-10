---
title: "System Architecture Model"
date: 2025-07-07
weight: 4
chapter: false
pre: " <b> 1.4 </b> "
---

The system is designed based on a **Client – Server – Cloud** architecture, ensuring flexibility, scalability, and security. The application consists of three main layers: **user interface** (frontend), **business logic processing** (backend), and **data storage** (database), all deployed on the AWS platform.

---

## General Workflow

### 🎯 **Frontend (Next.js)**

- Users interact through the dashboard: create projects, assign tasks, manage team members.
- Uses **Redux Toolkit** for state management and **RTK Query** for efficient API communication.
- Upon login, the frontend sends authentication details to **Cognito** and receives a **JWT token**, which is used for secure API requests.

### 🔐 **AWS Cognito**

- Handles user registration, login, password recovery, and multi-factor authentication (MFA).
- Returns a JWT token including **accessToken, idToken**, and **refreshToken.**
- Easily integrates with the Express backend to authenticate each API request.

### ⚙️ **Backend (Node.js + Express on EC2)**

- Receives requests from the frontend along with the **JWT token**.
- Verifies the token with **AWS Cognito**.
- Handles business logic: create/update projects, manage tasks, users, roles, etc.
- Connects to the **PostgreSQL** database via **Prisma ORM**.

### 🗃️ **Database (PostgreSQL on RDS)**

- Stores data about users, projects, tasks, and teams.
- Prisma ORM handles queries like select, insert, update, and delete in a safe and efficient way.
- Data is monitored and managed using **PgAdmin** during development.

---

## Optional Integrations

- 🗂️ **S3:** Stores attachments such as project documents, user profile images, etc. Easily integrated with the frontend.
- ⚡ **Lambda:** Executes lightweight functions like sending emails, handling events, updating status when a task is completed. No need for server maintenance.
- 🌐 **API Gateway:** Manages and secures **RESTful** endpoints in case the backend transitions to a serverless model (combining Lambda + API Gateway).

---

## System Diagrams

### 🧩 **Overall Architecture Diagram (AWS Architecture)**

<p align="center">
  <img src="/images/1.4/architecture.png" alt="Overall Architecture Diagram" style="max-width:600px; width:100%; display:block; margin:auto;" />
</p>

- Illustrates the main components: **Next.js → Cognito → EC2 → RDS**, with integrations to **S3, Lambda, API Gateway**.

### 🗂️ **Data Model Diagram**

<p align="center">
  <img src="/images/1.4/datamodel.png" alt="Data Model Diagram" style="max-width:600px; width:100%; display:block; margin:auto;" />
</p>

- Shows the relationships between tables: **User, Project, Task, Team, Priority, Status, ...**

### 🔐 **Cognito Authentication Flow**

- Describes the authentication process with Cognito: **Login → get token → use in API → role-based access on backend**.

  **Saving User:**

  <p align="center">
    <img src="/images/1.4/saving-user.png" style="max-width:800px; width:100%; display:block; margin:auto;" />
  </p>

  **Fetching User:**

  <p align="center">
    <img src="/images/1.4/fetching-user.png" style="max-width:800px; width:100%; display:block; margin:auto;" />
  </p>

  **Securing API:**

  <p align="center">
    <img src="/images/1.4/securing-api.png" style="max-width:800px; width:100%; display:block; margin:auto;" />
  </p>
