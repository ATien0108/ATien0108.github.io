---
title: "First Cloud Journey"
date: 2025-07-03
weight: 1
chapter: false
---

# Build a Project Management App with Next.js and Deploy on AWS

## 📝 PROJECT OVERVIEW

**Project Title**:  
**Building a Project Management Application using Next.js and deploying it on AWS**

**Project Objective**:  
Develop a modern web-based application that allows users to manage projects, tasks, and team members efficiently. The system supports user authentication, access control, real-time project tracking, and visualizes data through charts and data grids.

**Technologies Used**:

- **Frontend**: Next.js, Tailwind CSS, Material UI Data Grid, Redux Toolkit, Recharts, React DnD
- **Backend**: Node.js, Express, Prisma ORM, PostgreSQL
- **AWS Services**: Cognito, EC2, RDS, S3, Lambda, API Gateway

**System Architecture**:  
The application follows a **Client – Server – Cloud** model, ensuring scalability, flexibility, and security:

- The user interface is built with **Next.js**, interacting with the backend via RESTful APIs.
- The backend is developed using **Node.js + Express**, deployed on **Amazon EC2**, handling business logic and authentication.
- Data is stored and queried efficiently using **PostgreSQL on Amazon RDS**, accessed through **Prisma ORM**.
- Additional AWS services like **Cognito** (for authentication), **S3** (for file storage), **Lambda** (for lightweight processing), and **API Gateway** (for securing endpoints) enhance system reliability and scalability.

**Expected Outcome**:  
Deliver a fully functional project management dashboard with a modern UI, smooth user experience, and ready for deployment in real-world environments using AWS cloud infrastructure.
