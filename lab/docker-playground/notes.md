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
