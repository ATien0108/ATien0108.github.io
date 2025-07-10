---
title: "Connection Check"
date: 2025-07-09
weight: 2
chapter: false
pre: " <b> 5.2 </b> "
---

## Environment Preparation

Access root privileges to install system tools.

      sudo su -

Install NVM (Node Version Manager).

      curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

Reload the shell to use nvm:

      . ~/.nvm/nvm.sh

<p align="center">
<img src="/images/5.2/5.2.1.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Install the latest Node.js version:

      nvm install node

Check installed versions of Node and npm:

```bash
   node -v
```

```bash
   npm -v
```

<p align="center">
<img src="/images/5.2/5.2.2.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

## Install Git and Clone Project

Update system and install Git:

```bash
   sudo yum update -y
```

```bash
   sudo yum install git -y
```

Check Git version:

      git --version

<p align="center">
<img src="/images/5.2/5.2.3.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Clone the project source code from GitHub:

      git clone https://github.com/DyyyPhatt/project-management.git

Navigate to the backend (server) folder:

```bash
   ls
```

```bash
   cd project-management
```

```bash
   ls
```

```bash
   cd server
```

<p align="center">
<img src="/images/5.2/5.2.4.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

## Install and Run the Server

Install npm packages for the backend:

      npm i

Run the application in development mode:

      npm run dev

<p align="center">
<img src="/images/5.2/5.2.5.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Create .env file and set server port to 80:

      echo "PORT=80" > .env

Restart server using the new .env configuration:

      npm run dev

<p align="center">
<img src="/images/5.2/5.2.6.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Install and Configure PM2 for Background Process

Install PM2 to manage Node.js processes:

      npm i pm2 -g

Create PM2 config file (ecosystem.config.js):

      ls

<p align="center">
<img src="/images/5.2/5.2.7.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

      nano ecosystem.config.js

<p align="center">
<img src="/images/5.2/5.2.8.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Enable PM2 to auto-start on system boot:

      sudo env PATH=$PATH:$(which node) $(which pm2) startup systemd -u $USER --hp $(eval echo $USER)

<p align="center">
<img src="/images/5.2/5.2.9.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Start the server with PM2, check status, and monitor:

```bash
   pm2 start ecosystem.config.js
```

```bash
   pm2 status
```

<p align="center">
<img src="/images/5.2/5.2.10.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

      pm2 monit

<p align="center">
<img src="/images/5.2/5.2.11.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Stop and delete all current PM2 processes:

```bash
   pm2 stop all
```

```bash
   pm2 delete all
```

<p align="center">
<img src="/images/5.2/5.2.12.png"  style="max-width:800px; width:100%; height:auto; display:block; margin:auto;" />
</p>

Restart the server from the config:

      pm2 start ecosystem.config.js
