# Week 01

## Period

09 June 2026 – 12 June 2026

---

# Objectives

The objectives for this first week were:

- Initialize the CyberShield Range project.
- Define the project vision.
- Design the initial architecture.
- Define the laboratory infrastructure.
- Create project management workflows.
- Begin the Laboratory Environment phase.
- Install Docker on Ubuntu.

---

# Completed Work

## Project Foundation

The following project documents were created:

- Product Vision v1.0
- Architecture v1.0
- Cyber Lab Infrastructure v1.0
- CyberHealth Functional Specifications v1.0
- Docker Learning Environment v1.0
- Roadmap 24 Months

### GitHub Setup

Project management infrastructure was established:

- GitHub Repository created.
- LICENSE added.
- README added.
- CONTRIBUTING added.
- CHANGELOG added.
- GitHub Project Board configured.
- Milestone v0.1 Foundation completed.
- Milestone v0.2 Laboratory Environment created.
- Initial issues created and organized.

---

# Docker Laboratory

## Environment

Host Operating System:

```text
Ubuntu 24.04.4 LTS (Noble Numbat)
```

---

## Docker Installation

Successfully installed:

- Docker Engine
- Docker Compose Plugin

Validation performed using:

```bash
docker run hello-world
```

Result:

Docker installation completed successfully.

---

## Docker Concepts Learned

### Images

Downloaded images:

- hello-world
- ubuntu
- nginx

Learned how Docker images are used as templates for containers.

### Containers

Created and executed containers.

Commands explored:

```bash
docker run
docker ps
docker ps -a
docker stop
docker start
docker logs
```

### Volumes

Created:

```text
cybershield-data
```

Verified data persistence between containers.

### Networks

Created:

```text
cybershield-network
```

Network configuration:

```text
Subnet : 172.18.0.0/16
Gateway: 172.18.0.1
```

Tested communication between containers using Docker DNS.

Example:

```bash
ping test2
```

Result:

Successful communication between containers.

### Nginx Container

Created:

```text
playground-nginx
```

Port mapping:

```text
Host: 8080
Container: 80
```

Successfully accessed Nginx from the browser.

---

# Key Learnings

This week introduced the fundamental concepts required to build CyberShield Range:

- Docker Images
- Containers
- Volumes
- Networks
- Port Mapping
- Container Communication

A better understanding of Linux-based infrastructure and container networking was achieved.

---

# Challenges

No major technical issues encountered.

Areas requiring further study:

- Docker Compose
- Container Networking
- Reverse Proxy Configuration
- Persistent Storage Strategies

---

# Decisions Made

Several strategic decisions were made:

- CyberShield Range will be developed as a long-term Master project.
- CyberHealth will serve as the primary target application.
- Docker will be the standard deployment technology.
- The project will focus on practical cybersecurity and network security skills.

---

# Next Week Objectives

- Complete Docker Playground.
- Learn Docker Compose.
- Deploy MySQL in Docker.
- Containerize Laravel.
- Configure Nginx.
- Build the first CyberShield Range stack.

Target milestone:

v0.2 Laboratory Environment

---

# Personal Reflection

This week marked the official beginning of CyberShield Range.

The project evolved from an academic idea into a structured engineering project with documented objectives, architecture, roadmap and development workflow.

The first practical infrastructure components were successfully deployed using Docker, providing the foundation for future cybersecurity laboratories, attack simulations and detection systems.

The project now enters its implementation phase.
