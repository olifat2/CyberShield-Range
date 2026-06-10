# Docker Learning Environment v1.0

## Document Information

| Field        | Value             |
| ------------ | ----------------- |
| Project      | CyberShield Range |
| Version      | 1.0               |
| Status       | Draft             |
| Author       | Olivier Fatombi   |
| Last Updated | June 2026         |

---

# 1. Purpose

This document defines the Docker learning path and initial containerized environment required for CyberShield Range.

Docker will be used as the primary deployment technology for:

* application services;
* security tools;
* monitoring components;
* laboratory environments.

The objective is to acquire the necessary Docker skills while progressively building the CyberShield Range infrastructure.

---

# 2. Why Docker?

Docker provides:

* Environment isolation
* Reproducible deployments
* Simplified infrastructure management
* Service portability
* Easier experimentation

Docker is particularly suitable for cybersecurity laboratories because it allows multiple systems to interact within a controlled environment.

---

# 3. Learning Objectives

The following Docker concepts must be mastered.

## Level 1 — Fundamentals

Understand:

* Containers
* Images
* Volumes
* Networks
* Docker Hub

Skills:

* Pull images
* Run containers
* Stop containers
* Remove containers

---

## Level 2 — Container Management

Understand:

* Port mapping
* Persistent storage
* Environment variables

Skills:

* Configure containers
* Inspect containers
* Troubleshoot containers

---

## Level 3 — Docker Compose

Understand:

* Multi-container environments
* Service communication
* Infrastructure definition

Skills:

* Create docker-compose.yml files
* Launch multiple services
* Manage application stacks

---

## Level 4 — Security-Oriented Usage

Understand:

* Network segmentation
* Log collection
* Monitoring containers

Skills:

* Create isolated networks
* Monitor traffic
* Integrate security tools

---

# 4. CyberShield Range Learning Roadmap

## Stage 1

Deploy:

```text
Laravel
+
MySQL
```

Objective:

Understand multi-container applications.

---

## Stage 2

Add:

```text
Nginx
```

Objective:

Understand reverse proxy concepts.

---

## Stage 3

Add:

```text
Suricata
```

Objective:

Understand network monitoring.

---

## Stage 4

Add:

```text
Wazuh
```

Objective:

Centralize logs and security events.

---

## Stage 5

Add:

```text
AI Engine
```

Objective:

Prepare intelligent analysis capabilities.

---

# 5. Initial Learning Environment

Version 1.0 Environment:

```text
Ubuntu Host
│
├── Laravel Container
├── MySQL Container
└── Nginx Container
```

This environment serves as the first practical Docker laboratory.

---

# 6. Target Infrastructure

CyberShield Range Target Architecture:

```text
Ubuntu Host
│
├── CyberHealth
├── MySQL
├── Suricata
├── Wazuh
├── AI Engine
└── SOC Dashboard
```

---

# 7. Recommended Learning Resources

Official Documentation:

* Docker Documentation
* Docker Compose Documentation

Technical Practice:

* Container creation
* Volume management
* Network configuration
* Multi-container deployment

---

# 8. Success Criteria

Docker learning objectives are considered achieved when:

* Laravel runs inside Docker.
* MySQL runs inside Docker.
* Containers communicate successfully.
* Persistent storage is operational.
* Docker Compose manages the stack.

---

# 9. Expected Deliverables

The following deliverables are expected:

* Docker installed on Ubuntu.
* First Laravel container.
* First MySQL container.
* First docker-compose.yml.
* CyberHealth development environment.

---

# 10. Conclusion

Docker is a foundational technology for CyberShield Range.

Mastering Docker will enable the deployment of realistic cybersecurity laboratories while maintaining simplicity, reproducibility and scalability throughout the project lifecycle.
