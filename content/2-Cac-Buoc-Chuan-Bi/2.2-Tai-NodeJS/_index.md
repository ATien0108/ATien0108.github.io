---
title: "Install Node.js"
date: 2025-07-09
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

## Overview

**Node.js** is a server-side JavaScript runtime environment used to build the backend of this project. The backend leverages Node.js along with Express to handle APIs and connect to the database.

In addition to Node.js, the system also requires **npm** (Node Package Manager) — a tool for managing and installing dependencies for both frontend and backend.

Both the frontend (Next.js) and backend (Express.js) require Node.js to run and develop locally.

---

## Instructions

1. Go to the official Node.js download page: https://nodejs.org/en

2. Select the **LTS (Long Term Support)** version suitable for your operating system:

   - Windows: `.msi` installer
   - macOS: `.pkg` installer
   - Linux: choose the version that matches your distro

3. Download and install it like any other software (Next → Next → Install...).

4. Verify the installation by opening Terminal or Command Prompt and running:

   ```bash
   node -v
   npm -v
   ```
