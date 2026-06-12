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
