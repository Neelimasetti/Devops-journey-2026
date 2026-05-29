# Docker for DevOps 🐳

This section contains my Docker learning notes, hands-on labs, and practical exercises completed as part of my DevOps journey.

---

# Why Docker?

Before Docker, applications often worked on one machine but failed on another because of differences in:

* Operating Systems
* Libraries
* Dependencies
* Runtime environments

Docker solves this by packaging applications together with everything they need to run.

### Key Learning

**Build Once, Run Anywhere**

---

# Containers vs Virtual Machines

## Virtual Machines

* Each VM contains a full operating system
* Higher resource consumption
* Slower startup time

## Docker Containers

* Share the host operating system
* Lightweight
* Faster startup
* Efficient resource usage

### Analogy

Virtual Machine → Full Kitchen 🍳

Docker Container → Lunch Box 🍱

---

# Docker Core Components

## Docker Engine

Software responsible for running containers.

## Docker Image

A packaged blueprint containing:

* Application code
* Libraries
* Dependencies

Example:

```bash
docker pull nginx
```

---

## Docker Container

A running instance of a Docker image.

Example:

```bash
docker run nginx
```

---

## Docker Hub

Cloud repository used to store Docker images.

Examples:

* nginx
* ubuntu
* mysql

---

# Docker Workflow

```text
Create Image
      ↓
Push Image
      ↓
Docker Hub
      ↓
Pull Image
      ↓
Run Container
```

---

# Docker Lifecycle

Containers move through several states.

## Create

```bash
docker create nginx
```

## Start

```bash
docker start <container_id>
```

## Stop

```bash
docker stop <container_id>
```

## Remove

```bash
docker rm <container_id>
```

### Skills Learned

* Creating containers
* Starting containers
* Stopping containers
* Removing containers

---

# Interactive vs Detached Mode

## Interactive Mode

```bash
docker run -it ubuntu
```

Used for:

* Learning
* Testing
* Debugging

---

## Detached Mode

```bash
docker run -d nginx
```

Used for:

* Web servers
* Applications
* Production services

---

# Container Management

## List Running Containers

```bash
docker ps
```

## List All Containers

```bash
docker ps -a
```

## Restart Container

```bash
docker restart my-nginx
```

---

# Naming Containers

Instead of random names:

```bash
docker run -d --name my-nginx nginx
```

### Benefits

* Easier management
* Cleaner workflow
* Better troubleshooting

---

# Port Mapping

Containers are isolated by default.

Port mapping exposes container services.

Example:

```bash
docker run -d -p 8080:80 nginx
```

Meaning:

```text
Host Port 8080
      ↓
Container Port 80
```

Access:

```text
http://localhost:8080
```

---

# Logs & Troubleshooting

View logs:

```bash
docker logs my-nginx
```

Live logs:

```bash
docker logs -f my-nginx
```

### Skills Learned

* Monitoring containers
* Troubleshooting issues
* Viewing application output

---

# Accessing Containers

Enter running container:

```bash
docker exec -it my-nginx /bin/bash
```

Inside container:

```bash
ls
pwd
cat
```

### Skills Learned

* Inspect container filesystem
* Verify configurations
* Debug applications

---

# Docker Images

List images:

```bash
docker images
```

Download image:

```bash
docker pull nginx
```

Remove image:

```bash
docker rmi image_name
```

---

# Dockerfile

Dockerfile is used to create custom images.

Example:

```dockerfile
FROM ubuntu

COPY hello.txt /app/

CMD ["cat", "/app/hello.txt"]
```

Build image:

```bash
docker build -t myapp .
```

Run image:

```bash
docker run myapp
```

---

# NGINX Project

Created a simple web application using NGINX.

Example Dockerfile:

```dockerfile
FROM nginx

COPY index.html /usr/share/nginx/html/index.html
```

Build:

```bash
docker build -t myweb .
```

Run:

```bash
docker run -p 3000:80 myweb
```

Access:

```text
http://localhost:3000
```

---

# Docker Networking

Created custom network:

```bash
docker network create myapp-net
```

Purpose:

Allow containers to communicate with each other.

### Skills Learned

* Container communication
* Network isolation
* Service connectivity

---

# Docker Volumes

Volumes are used to persist data.

Create volume:

```bash
docker volume create mydata
```

Attach volume:

```bash
-v mydata:/var/lib/mysql
```

### Key Learning

Container can be deleted without losing data.

---

# MySQL + Adminer Lab

Practical project completed using:

* MySQL Container
* Adminer Container
* Docker Network
* Docker Volume

### Features Practiced

* Database creation
* Data insertion
* Container networking
* Persistent storage
* Browser-based database management

---

# Key Skills Gained

✅ Docker Fundamentals

✅ Images & Containers

✅ Lifecycle Management

✅ Port Mapping

✅ Logs & Troubleshooting

✅ Dockerfiles

✅ Custom Images

✅ NGINX Deployment

✅ Docker Networking

✅ Docker Volumes

✅ MySQL Persistence

---

# DevOps Relevance

Docker is one of the most important tools in modern DevOps.

These skills are directly used for:

* Application Packaging
* CI/CD Pipelines
* Cloud Deployments
* Microservices
* Kubernetes Workloads

Docker provides a consistent environment from development to production.
