# 🐳 🚀 Docker Containerization Guide

![Docker](https://img.shields.io/badge/Docker-Containerization-2496ED?style=for-the-badge&logo=docker)
![Platform](https://img.shields.io/badge/Platform-Linux-2CA5E0?style=for-the-badge&logo=linux)
![DevOps](https://img.shields.io/badge/DevOps-Tool-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

---

# 📌 What is Docker?

Docker is an open-source containerization platform that allows developers to package applications and their dependencies into lightweight, portable containers.

Containers ensure that applications run consistently across:

- 💻 Development Environment  
- 🧪 Testing Environment  
- 🚀 Production Environment  

---

# 🏗️ Why Docker?

✅ Lightweight  
✅ Fast Deployment  
✅ Environment Consistency  
✅ Portable Applications  
✅ Microservices Architecture Support  
✅ Easy Scaling  

---

# ⚙️ Docker Architecture

Docker works using:

- **Docker Client** → Runs docker commands  
- **Docker Daemon** → Manages containers  
- **Docker Images** → Blueprint of container  
- **Docker Containers** → Running instances of image  
- **Docker Registry** → Stores images (Docker Hub)  

---

# 🛠️ Installing Docker (Ubuntu/Linux)

```bash
# Update system
sudo apt update

# Install dependencies
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y

# Add Docker GPG Key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

# Add Docker Repository
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) stable"

# Install Docker
sudo apt update
sudo apt install docker-ce -y
```

---

# ✅ Verify Installation

```bash
docker --version
```

Check Docker service:

```bash
sudo systemctl status docker
```

---

# 👤 Run Docker Without sudo (Optional)

```bash
sudo usermod -aG docker $USER
newgrp docker
```

---

# 🐳 Core Docker Concepts

## 1️⃣ Docker Image

An image is a blueprint of application.

```bash
docker images
```

Pull image from Docker Hub:

```bash
docker pull nginx
```

---

## 2️⃣ Docker Container

A running instance of an image.

Run container:

```bash
docker run nginx
```

Run in detached mode:

```bash
docker run -d nginx
```

Run with port mapping:

```bash
docker run -d -p 8080:80 nginx
```

---

## 3️⃣ Dockerfile

Dockerfile is used to build custom images.

Example:

```dockerfile
FROM ubuntu:latest
RUN apt update
CMD ["echo", "Hello Docker"]
```

Build image:

```bash
docker build -t myimage .
```

---

## 4️⃣ Docker Volumes

Used to persist data.

```bash
docker volume create myvolume
```

Mount volume:

```bash
docker run -v myvolume:/data nginx
```

---

## 5️⃣ Docker Networks

Create network:

```bash
docker network create mynetwork
```

Run container inside network:

```bash
docker run --network mynetwork nginx
```

---

# 🔁 Common Docker Commands

```bash
docker ps                # Running containers
docker ps -a             # All containers
docker stop containerID
docker start containerID
docker restart containerID
docker rm containerID
docker rmi imageID
docker logs containerID
docker exec -it containerID bash
```

---

# 📦 Docker Compose

Docker Compose manages multi-container applications.

Install:

```bash
sudo apt install docker-compose -y
```

Example `docker-compose.yml`:

```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
```

Run:

```bash
docker-compose up -d
```

---

# 🔐 Docker Best Practices

✔️ Use Official Base Images  
✔️ Keep Images Small  
✔️ Use Multi-stage Builds  
✔️ Avoid Running as Root  
✔️ Use .dockerignore  
✔️ Tag Images Properly  

---

# 🌍 Where Docker is Used

- Microservices Architecture  
- CI/CD Pipelines  
- Kubernetes Deployment  
- Cloud Applications  
- DevOps Automation  

---

# 🆚 Virtual Machine vs Docker

| Virtual Machine | Docker Container |
|----------------|-----------------|
| Heavy | Lightweight |
| Full OS | Shared Kernel |
| Slow Boot | Fast Startup |
| More Resource Usage | Less Resource Usage |

---

# 🎯 Summary

Docker simplifies application deployment by packaging code and dependencies into containers.

It ensures:

- Consistency  
- Portability  
- Faster Development  
- Scalable Infrastructure  

---

