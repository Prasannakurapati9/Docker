
# 🐳 Docker Hands-On Lab

A hands-on project focused on understanding **Docker fundamentals, containerization, networking, persistent storage, Dockerfile, and Docker Compose**.

This repository documents the Docker concepts, commands, configurations, and practical exercises completed as part of my **DevOps learning journey**.

---

## 📌 Project Overview

Docker is a containerization platform that packages an application and its dependencies into a portable container.

In this lab, I practiced the complete basic Docker workflow:

```text
Docker Image
     ↓
Create / Run Container
     ↓
Configure Networking
     ↓
Attach Persistent Storage
     ↓
Build Custom Image with Dockerfile
     ↓
Manage Multiple Services with Docker Compose
```

---

## 🎯 Objectives

The main objectives of this project were to gain practical experience with:

* Docker images
* Docker containers
* Container lifecycle management
* Docker Hub
* Docker networking
* Port mapping
* Docker volumes
* Bind mounts
* Dockerfile
* Custom Docker images
* Docker Compose
* Multi-container applications

---

# 🐳 1. Docker Fundamentals

### Check Docker Version

```bash
docker --version
```

### Login to Docker Hub

```bash
docker login
```

### Search for an Image

```bash
docker search nginx
```

### Pull an Image

```bash
docker pull nginx
```

### List Images

```bash
docker images
```

or

```bash
docker image ls
```

### Inspect an Image

```bash
docker inspect nginx
```

### View Image History

```bash
docker history nginx
```

### Remove an Image

```bash
docker rmi nginx
```

---

# 📦 2. Docker Containers

A **container** is a running or stopped instance of a Docker image.

### Create a Container

```bash
docker create --name nginx_srv01 nginx
```

`docker create` creates the container but does not start it.

### Start a Container

```bash
docker start nginx_srv01
```

### Stop a Container

```bash
docker stop nginx_srv01
```

### List Running Containers

```bash
docker ps
```

### List All Containers

```bash
docker ps -a
```

### Run a Container

```bash
docker run --name nginx_srv02 nginx
```

`docker run` creates and starts a container.

### Run in Detached Mode

```bash
docker run -d --name nginx_srv03 nginx
```

The `-d` option runs the container in the background.

### Access a Running Container

```bash
docker exec -it nginx_srv03 /bin/bash
```

### Exit the Container

```bash
exit
```

### Force Stop a Container

```bash
docker kill nginx_srv03
```

### Remove a Container

```bash
docker rm nginx_srv03
```

---

# 🌐 3. Docker Networking

Docker networking allows containers to communicate with other containers and external systems.

### List Docker Networks

```bash
docker network ls
```

## Bridge Network

The bridge network is the standard networking mode for containers.

Example:

```bash
docker run -d \
  --name nginx_srv04 \
  -p 8080:80 \
  nginx
```

Here:

```text
Docker Host Port 8080
        ↓
Container Port 80
        ↓
      Nginx
```

The `-p 8080:80` option publishes container port `80` on host port `8080`.

## Host Network

```bash
docker run -d \
  --name nginx_host \
  --network host \
  nginx
```

The container uses the host's network namespace.

## None Network

```bash
docker run -d \
  --name nginx_none \
  --network none \
  nginx
```

This isolates the container from external network
