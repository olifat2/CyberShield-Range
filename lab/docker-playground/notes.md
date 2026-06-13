# Docker Playground Notes

## Images

An image is a template used to create containers.

Example:

docker pull nginx

---

## Containers

A container is a running instance of an image.

Example:

docker run nginx

---

## Port Mapping

Example:

docker run -d -p 8080:80 nginx

Meaning:

Host Port 8080 -> Container Port 80

## Volumes

A Docker volume stores persistent data independently from containers.

Example:

docker volume create cybershield-data

Container:

docker run -v cybershield-data:/data ubuntu

Benefits:

- Data persistence
- Backup support
- Database storage
- Shared data between containers

## Docker Networks

Created a custom Docker bridge network:

docker network create cybershield-network

Network configuration:

- Subnet: 172.18.0.0/16
- Gateway: 172.18.0.1

Tested container-to-container communication using ping.

Result:

test1 successfully resolved and reached test2 using Docker DNS.

Key learning:

Containers on the same Docker network can communicate using service names rather than IP addresses.

## Docker Compose

Docker Compose allows defining and running multi-container applications.

Example:

docker compose up -d

Benefits:

- Infrastructure as Code
- Reproducibility
- Simplified deployments
- Multi-service orchestration

First service deployed:

- Nginx
- Port 8081
