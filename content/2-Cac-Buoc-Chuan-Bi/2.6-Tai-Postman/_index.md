---
title: "Install Postman"
date: 2025-07-09
weight: 6
chapter: false
pre: " <b> 2.6 </b> "
---

## Overview

**Postman** is one of the most popular tools for testing APIs. It allows developers to:

- Send HTTP requests (GET, POST, PUT, DELETE, PATCH) to the backend server.
- Add headers, body, and tokens to test authentication.
- View API responses directly.
- Save requests into **collections** for reuse.

In this project, Postman is used to:

- Test the functionality of APIs provided by the **Express backend**.
- Send authentication tokens from **Cognito** to verify authorization.
- Quickly test features like creating projects, tasks, and users before integrating with the frontend.

---

## Instructions

1. Visit the official Postman download page:  
   👉 https://www.postman.com/downloads/

2. Choose the correct version for your operating system:

   - **Windows**: `.exe` installer
   - **macOS**: `.zip` or `.dmg` file
   - **Linux**: `.tar.gz` or AppImage

3. Install the application as you would any standard software.  
   After launching Postman, you can sign in (or click “Skip and take me to the app”).

4. The main Postman interface includes:

   - **Request URL**: where you input the API endpoint.
   - **Method**: select HTTP method (GET, POST, etc.).
   - **Headers**: add key-value pairs like `Authorization: Bearer [token]`.
   - **Body**: used with POST/PUT to send JSON data.

5. Create a dedicated **Collection** for your project to store frequently used requests (e.g., `Login`, `Get All Projects`, `Create Task`, ...).
