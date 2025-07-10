---
title: "Introduction"
date: 2025-07-07

weight: 1
chapter: false
pre: " <b> 1. </b> "
---

**Main Objective of the Project:**

The **Project Management Dashboard** is a modern web-based platform that allows users to create, assign, and track projects in real time. It features an intuitive interface with integrated charts and data tables to enhance team productivity.

---

## Project Goals

- Manage projects, tasks, team members, and project progress.
- Implement clear and secure user role permissions.
- Update statuses and data in real time.
- Support task drag-and-drop and visualize using charts.
- Deploy flexibly on AWS cloud infrastructure.

---

## Technologies Used

### Frontend

- **Next.js:** React framework with SSR/SSG support, optimized for speed and SEO.
- **Tailwind CSS:** Utility-first CSS framework for responsive design.
- **Material UI Data Grid:** Powerful data table with sorting, filtering, and pagination.
- **Redux Toolkit + RTK Query:** Efficient state management and API handling.
- **React DnD:** Drag-and-drop task management.
- **Recharts:** Visualize data with bar, pie, and line charts.

### Backend

- **Node.js + Express:** Provides RESTful API services.
- **TypeScript:** Enhances code clarity and type safety.
- **Prisma ORM + PostgreSQL:** Efficient and maintainable relational database communication.
- **PgAdmin, Postman:** Tools for database management and API testing during development.

---

## Integrated AWS Services

- **Amazon Cognito:** User authentication and authorization with JWT tokens.
- **Amazon EC2:** Hosts the Node.js backend server.
- **Amazon RDS (PostgreSQL):** Managed relational data storage.
- **Amazon S3:** Stores images and attachments.
- **AWS Lambda:** Handles small, serverless tasks like sending emails and automation.
- **Amazon API Gateway:** Manages and secures API endpoints.

---

## System Architecture Overview

The system follows a **Client – Server – Cloud** model with three main layers:

1. **Frontend (Next.js):** Users interact with the dashboard UI and send JWT tokens with API requests.
2. **Backend (Express on EC2):** Handles business logic, token verification, and database operations.
3. **Database (RDS – PostgreSQL):** Stores project, user, and task information.

**Extended Integrations:**

- **S3:** Stores images and attachments.
- **Lambda:** Executes automated functions based on events.
- **API Gateway:** Manages API endpoints for serverless architecture.

---

**System Architecture Diagram:**  
Next.js → Cognito → EC2 (Express) → RDS (PostgreSQL)  
Extended services: S3, Lambda, API Gateway
