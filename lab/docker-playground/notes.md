# Docker Playground Notes

## Overview

This document contains the key concepts learned while building the CyberShield Range laboratory environment.

---

# Docker Fundamentals

## What is Docker?

Docker is a containerization platform that allows applications and services to run in isolated environments called containers.

Benefits:

* Portability
* Isolation
* Scalability
* Reproducibility
* Simplified deployment

---

# Images

An image is a template used to create containers.

Examples:

```bash
docker pull ubuntu
docker pull nginx
docker pull mysql
```

List available images:

```bash
docker images
```

Key learning:

* Images are read-only templates.
* Containers are created from images.

---

# Containers

A container is a running instance of an image.

Examples:

```bash
docker run ubuntu
docker run nginx
```

List running containers:

```bash
docker ps
```

List all containers:

```bash
docker ps -a
```

Container lifecycle:

```bash
docker start <container>
docker stop <container>
docker rm <container>
```

Key learning:

* Containers are isolated environments.
* Containers can be created and destroyed quickly.

---

# Interactive Containers

Example:

```bash
docker run -it ubuntu bash
```

Inside the container:

```bash
cat /etc/os-release
```

Observation:

Host OS:

```text
Ubuntu 24.04.4 LTS
```

Container OS:

```text
Ubuntu 26.04 LTS
```

Key learning:

Containers can run operating system environments different from the host.

---

# Port Mapping

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

Key learning:

Docker can expose services running inside containers to external users.

---

# Docker Volumes

Volumes store persistent data independently from containers.

Create a volume:

```bash
docker volume create cybershield-data
```

List volumes:

```bash
docker volume ls
```

Inspect volume:

```bash
docker volume inspect cybershield-data
```

Example:

```bash
docker run -it \
-v cybershield-data:/data \
ubuntu bash
```

Created file:

```bash
echo "CyberShield Range" > /data/project.txt
```

Verification:

```bash
cat /data/project.txt
```

Result:

```text
CyberShield Range
```

Key learning:

* Data survives container removal.
* Volumes are essential for databases.

---

# Docker Networks

Docker networks allow containers to communicate securely.

Create network:

```bash
docker network create cybershield-network
```

List networks:

```bash
docker network ls
```

Inspect network:

```bash
docker network inspect cybershield-network
```

Configuration observed:

```text
Subnet : 172.18.0.0/16
Gateway: 172.18.0.1
```

Key learning:

* Containers on the same network communicate directly.
* Docker provides built-in DNS resolution.

---

# Container-to-Container Communication

Containers created:

```text
test1
test2
```

Communication test:

```bash
ping test2
```

Result:

```text
PING test2 (172.18.0.3)
```

Key learning:

Containers can communicate using names instead of IP addresses.

---

# Docker Compose

Docker Compose allows defining infrastructure as code.

Example file:

```yaml
services:
  nginx:
    image: nginx:latest
    container_name: playground-nginx-compose
    ports:
      - "8081:80"
```

Start services:

```bash
docker compose up -d
```

Stop services:

```bash
docker compose down
```

View logs:

```bash
docker compose logs
```

Key learning:

* Infrastructure becomes reproducible.
* Multiple services can be managed together.

---

# Nginx Service Deployment

Deployed service:

```text
playground-nginx-compose
```

Port mapping:

```text
8081 → 80
```

Verification:

```text
http://localhost:8081
```

Result:

```text
Welcome to nginx!
```

---

# MySQL Deployment

Service:

```text
playground-mysql
```

Database:

```text
cyberhealth
```

User:

```text
cyberuser
```

Configuration:

```yaml
MYSQL_ROOT_PASSWORD
MYSQL_DATABASE
MYSQL_USER
MYSQL_PASSWORD
```

Verification:

```text
MySQL Server ready for connections
```

Key learning:

* Databases can be fully containerized.
* Persistent storage is achieved using Docker volumes.

---

# Relevance to CyberShield Range

These concepts will be used to build:

```text
CyberHealth
│
├── Laravel Application
├── MySQL Database
├── Nginx Reverse Proxy
├── Wazuh
├── Suricata
├── AI Detection Engine
└── SOC Dashboard
```

The laboratory environment serves as the foundation for future cybersecurity simulations and detection systems.

---

# Current Skills Acquired

* Docker Installation
* Images
* Containers
* Interactive Containers
* Port Mapping
* Volumes
* Networks
* Docker DNS
* Container Communication
* Docker Compose
* Nginx Deployment
* MySQL Deployment

Status:

CyberShield Range Laboratory Environment successfully initialized.
