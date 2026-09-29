# 🐳 Docker Hands-On Lab

A hands-on project covering **Docker fundamentals, containerization, networking, storage, Dockerfile, and Docker Compose** as part of my DevOps learning journey.

## 📌 Topics Covered

* Docker Images
* Docker Containers
* Docker Hub
* Container Lifecycle Management
* Docker Networking
* Port Mapping
* Docker Volumes
* Bind Mounts
* Dockerfile
* Custom Docker Images
* Docker Compose
* Multi-container Applications

## 🐳 Docker Basics

```bash
docker --version
docker login
docker search nginx
docker pull nginx

docker images
docker inspect nginx
docker history nginx
```

## 📦 Container Management

```bash
docker create --name nginx01 nginx
docker run -d --name nginx02 nginx

docker ps
docker ps -a

docker start nginx01
docker stop nginx01
docker exec -it nginx02 /bin/bash

docker rm nginx02
docker rmi nginx
```

## 🌐 Networking

```bash
docker network ls

docker run -d --name web -p 8080:80 nginx

docker run -d --name web-host --network host nginx
docker run -d --name web-none --network none nginx
```

Practiced **bridge networking, host networking, none networking, and port mapping**.

## 💾 Volumes & Storage

```bash
docker volume create appdata
docker volume ls
docker volume inspect appdata

docker run -it \
  --mount source=appdata,destination=/data \
  centos
```

Also practiced:

* Docker volumes
* Bind mounts
* Persistent data
* Sharing volumes between containers

## 🛠️ Dockerfile

Created custom Docker images using common Dockerfile instructions:

```dockerfile
FROM
WORKDIR
COPY
RUN
EXPOSE
CMD
```

Example:

```bash
docker build -t myapp:v1 .
docker run -d --name myapp myapp:v1
```

## ⚙️ Docker Compose

Used Docker Compose to define and manage **multi-container applications**.

```yaml
services:
  web:
    image: nginx
    ports:
      - "8080:80"

  app:
    build: .

  db:
    image: mysql
```

Common commands practiced:

```bash
docker compose up -d
docker compose ps
docker compose logs
docker compose stop
docker compose start
docker compose down
```

## 🎯 Key Learning

This project helped me understand the basic Docker workflow:

**Image → Container → Network → Storage → Dockerfile → Docker Compose**

I focused on understanding how Docker is used to **build, run, connect, and manage containerized applications**.

### 🧰 Technologies

**Docker | Dockerfile | Docker Compose | Linux | Nginx  | Containerization**
