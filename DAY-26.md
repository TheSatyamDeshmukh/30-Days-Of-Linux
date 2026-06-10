# Day 26 🐳 — Docker on Linux

> **"Docker = Apne program ko ek 'dibba' mein band karo — kahan bhi chalaao!"**

---

## 🤔 Docker Kya Hai?

**Analogy:** Socho tumne ek dish banaayi — Delhi mein badhiya bani. Ab Mumbai mein banana chahte ho, lekin wahan ingredients alag hain, tools alag hain — dish waisi nahi banti!

Docker matlab — **poori kitchen ko ek box mein band karo** — box kahan bhi le jao, dish same banti hai!

```
Traditional:             Docker:
Dev ka PC    ≠   Server  Dev ka PC    =   Server
(Works here!)  (Breaks!) (Same container everywhere!)
```

---

## 🚀 Docker Install karo

```bash
# Ubuntu pe:
sudo apt update
sudo apt install docker.io

# Ya official script se:
curl -fsSL https://get.docker.com | sudo sh

# Service start karo
sudo systemctl start docker
sudo systemctl enable docker

# Bina sudo ke docker chalao
sudo usermod -aG docker $USER
newgrp docker              # Ya logout/login karo

# Test karo
docker --version
docker run hello-world     # Pehla container!
```

---

## 📦 Basic Docker Commands

```bash
# Images
docker images              # Local images list karo
docker pull ubuntu         # Image download karo
docker pull nginx:latest   # Specific tag
docker rmi image_id        # Image delete karo

# Containers
docker ps                  # Running containers
docker ps -a               # Sab containers (stopped bhi)
docker run ubuntu          # Container run karo
docker run -it ubuntu bash # Interactive terminal ke saath
docker run -d nginx        # Background mein run karo (-d = detach)
docker run -p 8080:80 nginx # Port map karo (host:container)
docker run --name mycontainer nginx  # Naam do

# Container Control
docker stop container_id   # Stop karo
docker start container_id  # Start karo
docker restart container_id
docker rm container_id     # Delete karo
docker rm -f container_id  # Force delete (running bhi)

# Logs & Info
docker logs container_id   # Logs dekho
docker logs -f container_id # Live logs
docker inspect container_id # Detailed info
docker stats               # Live resource usage
```

---

## 🏗️ Dockerfile — Apna Image Banao

```dockerfile
# Dockerfile
FROM ubuntu:22.04                  # Base image

LABEL maintainer="tumhara@email.com"

# Environment variable
ENV APP_DIR=/app

# Commands run karo (image build ke waqt)
RUN apt update && apt install -y python3 python3-pip

# Working directory set karo
WORKDIR $APP_DIR

# Files copy karo
COPY requirements.txt .
COPY app.py .

# Dependencies install karo
RUN pip3 install -r requirements.txt

# Port expose karo
EXPOSE 5000

# Container start hone pe yeh chalega
CMD ["python3", "app.py"]
```

```bash
# Image build karo
docker build -t myapp:1.0 .

# Run karo
docker run -p 5000:5000 myapp:1.0
```

---

## 🔗 Docker Networking

```bash
docker network ls              # Networks list karo
docker network create mynet    # Network banao
docker run --network mynet nginx  # Container network mein add karo
```

---

## 💾 Docker Volumes — Data Persist Karo

```bash
# Volume banao
docker volume create mydata

# Container mein mount karo
docker run -v mydata:/app/data nginx

# Local folder mount karo
docker run -v /home/rahul/data:/app/data nginx

# Volumes list karo
docker volume ls
```

---

## 🐙 Docker Compose — Multiple Containers

```yaml
# docker-compose.yml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
    volumes:
      - ./html:/usr/share/nginx/html
  
  db:
    image: mysql:8
    environment:
      MYSQL_ROOT_PASSWORD: secret
      MYSQL_DATABASE: myapp
    volumes:
      - dbdata:/var/lib/mysql

volumes:
  dbdata:
```

```bash
docker compose up -d       # Start karo (background)
docker compose down        # Stop + remove karo
docker compose logs        # Logs dekho
docker compose ps          # Status dekho
```

---

## 🏋️ Practice

```bash
# Step 1: Docker install confirm karo
docker --version

# Step 2: Hello World
docker run hello-world

# Step 3: Ubuntu container interactive
docker run -it ubuntu bash
# Andar jao:
apt update
apt install -y curl
curl --version
exit

# Step 4: Nginx web server
docker run -d -p 8080:80 --name webserver nginx
# Browser mein kholun: http://localhost:8080

# Step 5: Dekho aur saaf karo
docker ps
docker stop webserver
docker rm webserver
```

---

## 📝 Aaj Ka Summary

✅ Docker = Application ko container mein pack karo
✅ `docker run` — container start karo
✅ `docker ps` — running containers
✅ `docker build` — image banao Dockerfile se
✅ `-p 8080:80` — port mapping
✅ `-v` — volume mount
✅ Docker Compose — multiple containers manage karo

---
**Day:** 26/30 | **Topic:** Docker on Linux | **Difficulty:** ⭐⭐⭐⭐☆
