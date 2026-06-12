# WEEK 01

## Period

June 2026

---

## Objectives

* Complete CyberShield Range v0.1 Foundation
* Create project documentation
* Initialize v0.2 Laboratory Environment
* Install Docker on Ubuntu

---

## Activities

### Docker Installation

#### Environment

Operating System:

```text
Ubuntu 24.04.4 LTS (Noble Numbat)
```

#### Step 1 — Remove Previous Docker Versions

```bash
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do
  sudo apt-get remove $pkg
done
```

#### Step 2 — Update System

```bash
sudo apt update
sudo apt upgrade -y
```

#### Step 3 — Install Dependencies

```bash
sudo apt install -y ca-certificates curl gnupg
```

#### Step 4 — Add Docker GPG Key

```bash
sudo install -m 0755 -d /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

#### Step 5 — Add Docker Repository

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) \
  signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

#### Step 6 — Install Docker Engine and Docker Compose

```bash
sudo apt update

sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

#### Step 7 — Verify Installation

```bash
docker --version
docker compose version
```

#### Step 8 — Run First Container

```bash
sudo docker run hello-world
```

---

## Lessons Learned

### Image

Une image est un modèle. Elle sert à créer des conteneurs. L'image ne s'exécute pas.

### Container

Un conteneur est une instance en cours d'exécution d'une image.

---

## Challenges

(To be completed)

---

## Next Steps

* Verify Docker installation
* Configure Docker permissions
* Learn Docker fundamentals
* Create CyberShield Docker Playground

---

## Personal Reflection

CyberShield Range officially entered the implementation phase.

The laboratory environment milestone (v0.2) has started with Docker installation on Ubuntu 24.04 LTS. This marks the beginning of the practical infrastructure work that will support future cybersecurity simulations and detection mechanisms.
