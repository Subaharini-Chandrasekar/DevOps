# 🚀 Day 3 – Docker, Nginx & Jenkins Hands-on

![Docker](https://img.shields.io/badge/Docker-Container-blue?style=for-the-badge&logo=docker)
![Nginx](https://img.shields.io/badge/Nginx-WebServer-green?style=for-the-badge&logo=nginx)
![Jenkins](https://img.shields.io/badge/Jenkins-CI/CD-red?style=for-the-badge&logo=jenkins)
![NodeJS](https://img.shields.io/badge/Node.js-Backend-brightgreen?style=for-the-badge&logo=node.js)

---

# 🎯 Objectives

- Work with a free web project template  
- Build a custom Docker image for a Node.js app  
- Understand NGINX deployment workflow using Docker  
- Learn basic Jenkins installation and setup  
- Practice container lifecycle commands (run, stop, remove)  

---

# 🧩 Part 1: Getting a Free Project

- Choose a free web template from any template website  
- Use it as a sample Web / Node / React project  
- This project will be used for Docker build and deployment  

---

# 🐳 Part 2: Build Custom Docker Image (Node App)

## 🔨 Build Image

```bash
docker build -t mywebsite:v1 .
```

## 📦 Check Images

```bash
docker images
```

## ▶️ Run and Test Container

```bash
docker run -d -p 3000:3000 mywebsite:v1
docker ps
```

## 🛑 Stop and Remove Container

```bash
docker stop <container_id>
docker rm <container_id>
```

---

# 🌐 Part 3: NGINX Workflow with Docker

## 1️⃣ Pull Nginx Image

```bash
docker pull nginx:alpine
docker images
```

## 2️⃣ Test Nginx

```bash
docker run -d -p 8080:80 nginx:alpine
docker ps
```

### Test in Browser or Terminal

```bash
curl localhost:8080
```

### Stop and Remove Test Container

```bash
docker stop <container_id>
docker rm <container_id>
```

---

# 🏗️ Part 4: Build Your React / Web App

Install dependencies and build project:

```bash
npm install
npm run build
```

This will create a folder like:

```
dist/
# or
build/
```

---

# 🚀 Part 5: Deploy Web App into Nginx Using Docker

Run Nginx with volume mapping:

```bash
docker run -d \
  --name mynginx \
  -p 8080:80 \
  -v $(pwd)/dist:/usr/share/nginx/html \
  nginx:alpine
```

## 🔍 Check Running Containers

```bash
docker ps
```

## 🌍 Test in Browser

```
http://localhost:8080
```

---

# 🛑 Part 6: Stop and Delete Container

```bash
docker stop mynginx
docker rm mynginx
```

---

# ☀️ Afternoon Session: Jenkins Installation & Setup

---

## 1️⃣ Update System

```bash
sudo apt update
sudo apt upgrade -y
```

---

## 2️⃣ Install Java (Jenkins Requirement)

Check Java:

```bash
java -version
```

If not installed:

```bash
sudo apt install openjdk-17-jdk -y
```

Verify:

```bash
java -version
```

---

## 3️⃣ Add Jenkins Repository Key

```bash
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
```

---

## 4️⃣ Add Jenkins Repository

```bash
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
```

---

## 5️⃣ Install Jenkins

```bash
sudo apt update
sudo apt install jenkins -y
```

---

## 6️⃣ Start and Enable Jenkins

```bash
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins
```

---

## 7️⃣ Open Jenkins in Browser

Default URL:

```
http://localhost:8080
```

If firewall is enabled:

```bash
sudo ufw allow 8080
sudo ufw reload
```

Restart Jenkins if needed:

```bash
sudo systemctl restart jenkins
```

---

# 📝 Summary

✅ Docker is used to build and run applications inside containers  
✅ Nginx is used as a web server to serve built frontend applications  
✅ Containers can be started, stopped, and removed using Docker commands  
✅ Jenkins is used for automation and CI/CD  
✅ This session covered image building, container management, and web deployment  

---
