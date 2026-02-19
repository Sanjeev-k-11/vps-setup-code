# 🚀 Production Deployment Bible
### **Full-Stack Managed Environment (Nginx + PM2 + React + Node.js + MongoDB)**

![Server Status](https://img.shields.io/badge/Server-Ubuntu_Linux-orange?style=for-the-badge&logo=ubuntu&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-Reverse_Proxy-green?style=for-the-badge&logo=nginx&logoColor=white)
![PM2](https://img.shields.io/badge/PM2-Process_Manager-blue?style=for-the-badge&logo=pm2&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-Database-47A248?style=for-the-badge&logo=mongodb&logoColor=white)

---

## 📑 Table of Contents
1. [📝 Editing Files (Nano)](#-1-editing-files-nano)
2. [⚙️ Backend Management (PM2)](#-2-backend-management-pm2)
3. [🍃 Database Management (MongoDB)](#-3-database-management-mongodb)
4. [🏗️ Frontend Build & Update](#-4-frontend-build--update)
5. [🌐 Nginx Administration](#-5-nginx-administration)
6. [🔄 The Golden Deployment Flow](#-the-golden-deployment-flow)
7. [🛠️ Troubleshooting](#-troubleshooting)

---

## 📝 1. Editing Files (Nano)
Nano is the default terminal editor for modifying `.env` or config files.

| Action | Command / Shortcut |
| :--- | :--- |
| **Open File** | `nano <filename>` |
| **Save Changes** | `CTRL + O` then press `ENTER` |
| **Exit Editor** | `CTRL + X` |
| **Search Text** | `CTRL + W` |

---

## ⚙️ 2. Backend Management (PM2)
PM2 ensures your Node.js API stays online 24/7 with automatic restarts.

```bash
# Check status of all apps
pm2 status

# Restarting logic
pm2 restart all             # Restart everything
pm2 restart <app_name>      # Restart specific app

# Monitoring & Logs
pm2 logs                    # View real-time error/output logs
pm2 monit                   # Open interactive dashboard

## if you are updated all deta all backend the
pm2 start Server.js --name goride


# Persistence
pm2 save                    # Keeps apps running after server reboot

```


@@ 🏗️ 4. Frontend Build & Update

For React/Vite apps, generate a production build and move it to the Nginx root.

```bash

# 1. Navigate to frontend & Build
cd frontend
npm install
npm run build

# 2. Deploy to Nginx public folder
sudo rm -rf /var/www/html/*
sudo cp -r dist/* /var/www/html/
```
## 🌐 5. Nginx Administration

Nginx handles incoming web traffic and routes it to your frontend or API.

```bash
# 🧪 Step 1: ALWAYS test config before restarting
sudo nginx -t

# 🔄 Step 2: Reload or Restart
sudo systemctl reload nginx    # Hot-reload (No downtime)
sudo systemctl restart nginx   # Full restart
```




