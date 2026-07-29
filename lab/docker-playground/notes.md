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

# Lessons Learned

## Lesson 01 - Docker Installation

### Challenge

Docker was not previously installed on the development environment.

### Solution

Installed Docker Engine and Docker Compose using the official Docker repository.

### Knowledge Acquired

* Docker installation process
* Package repositories
* Docker daemon architecture

---

## Lesson 02 - Understanding Images and Containers

### Challenge

Initially confusing Docker images with containers.

### Solution

Practiced with Ubuntu and Nginx images.

### Knowledge Acquired

Image:

```text
Template
```

Container:

```text
Running instance of an image
```

Relationship:

```text
Image
   ↓
Container
```

---

## Lesson 03 - Port Mapping

### Challenge

Understanding how services inside containers become accessible from the host.

### Solution

Used Nginx:

```bash
docker run -d -p 8080:80 nginx
```

### Knowledge Acquired

```text
Host Port → Container Port
```

Example:

```text
8080 → 80
```

---

## Lesson 04 - Persistent Storage

### Challenge

Understanding what happens when a container is deleted.

### Solution

Created a Docker volume.

```bash
docker volume create cybershield-data
```

Stored test data inside the volume.

### Knowledge Acquired

Containers are ephemeral.

Volumes preserve data.

```text
Container deleted
       ↓
Data survives
```

---

## Lesson 05 - Docker Networks

### Challenge

Understanding communication between containers.

### Solution

Created a custom network.

```bash
docker network create cybershield-network
```

Tested connectivity:

```bash
ping test2
```

### Knowledge Acquired

Docker provides:

* Internal DNS
* Service discovery
* Network isolation

Example:

```text
test1
   ↓
Docker DNS
   ↓
test2
```

---

## Lesson 06 - Docker Compose

### Challenge

Managing containers individually becomes difficult.

### Solution

Created a Docker Compose configuration.

```yaml
services:
  nginx:
    image: nginx
```

### Knowledge Acquired

Infrastructure can be described as code.

Benefits:

* Reproducibility
* Simplicity
* Version control

---

## Lesson 07 - MySQL Container Deployment

### Challenge

Deploying a database inside Docker.

### Solution

Configured MySQL with environment variables.

### Knowledge Acquired

* Database initialization
* Environment variables
* Persistent storage
* Database users

Example:

```env
MYSQL_DATABASE=cyberhealth
MYSQL_USER=cyberuser
```

---

## Lesson 08 - Laravel Containerization

### Challenge

Running a Laravel application inside Docker.

### Solution

Created:

* Dockerfile
* Docker Compose configuration

Built custom image:

```bash
docker compose build
```

### Knowledge Acquired

* PHP-FPM containers
* Docker build process
* Application containerization

---

## Lesson 09 - Slow Docker Builds

### Challenge

Initial image build required a long time.

### Observation

First build:

```text
~16 minutes
```

### Cause

* Base image download
* Dependency installation
* Empty Docker cache

### Knowledge Acquired

Subsequent builds are faster because Docker reuses cached layers.

---

## Personal Reflection

Current progress demonstrates the transition from:

```text
Application Development
```

to:

```text
Infrastructure Engineering
```

The project is no longer limited to software development.

It now includes:

* System administration
* Networking
* DevOps
* Containerization
* Cybersecurity architecture

These competencies are essential for the future CyberShield Range platform.
