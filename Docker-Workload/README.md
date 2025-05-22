# 🐳 Voting App Docker Deployment

This guide explains how to deploy the **Docker-based Voting App** on an Ubuntu EC2 instance using Docker Compose. It supports two modes:

- ✅ Building images locally
- 📦 Using pre-built images from Docker Hub

---

## 📁 Folder Structure

```
k8s-voting-app/
├── Docker-Workload/
│   ├── docker-compose.yml           # Defines local development using build: contexts
│   ├── docker-compose.images.yml    # Uses prebuilt images from Docker Hub for quick setup
├── vote/
├── result/
├── worker/
├── seed-data/
├── healthchecks/

---

## 🧾 Prerequisites

- Ubuntu EC2 instance (tested on Ubuntu 20.04+)
- Docker installed
- Docker Compose v2 installed

### 🔧 Install Docker & Docker Compose

```bash
sudo apt update
sudo apt install -y docker.io docker-compose-plugin
sudo systemctl start docker
sudo systemctl enable docker
```

## 🚀 Deployment Options

### 🔧 Option 1: Build Images Locally
Use this when you want to build your own app images from source code.

```bash
cd ~/k8s-voting-app/Docker-Workload
docker compose -f docker-compose.yml up -d --build
```

### 📦 Option 2: Use Prebuilt Images
Use this if you don’t want to build locally and want faster setup using Docker Hub images.

```bash
cd ~/k8s-voting-app/Docker-Workload
docker compose -f docker-compose.images.yml up -d
```

### 🧪 Option 3: Combined Build & Images (Advanced)
Use both files if you want to override only certain services with local builds and use prebuilt images for others.

```bash
cd ~/k8s-voting-app/Docker-Workload
docker compose -f docker-compose.yml -f docker-compose.images.yml up -d --build
```

## 🧠 Understanding the Two Compose Files

| File                     | Purpose                                         |
|--------------------------|-------------------------------------------------|
| docker-compose.yml       | Defines local development using `build:` contexts |
| docker-compose.images.yml| Uses prebuilt images from Docker Hub for quick setup |

👉 When using both files with `-f`, the later file overrides the earlier one.

## ✅ Verify Deployment

### 🔍 Check Running Containers

```bash
docker ps
```

Example output:

```bash
CONTAINER ID   IMAGE                                  PORTS                    NAMES
abc123         dockersamples/examplevotingapp_vote    0.0.0.0:5000->80/tcp     docker-workload-vote-1
def456         postgres:15-alpine                     5432/tcp                 docker-workload-db-1
```

### 📜 View Logs

```bash
docker compose logs -f
```

## 🌐 Access the App

🗳️ Voting UI: http://<your-ec2-public-ip>:5000  
📊 Results UI: http://<your-ec2-public-ip>:5001

✅ Open these ports in your EC2 security group:

- TCP 5000 (Voting UI)
- TCP 5001 (Result UI)

## 🛑 Stop & Clean Up

To stop and remove all containers:

```bash
docker compose down
```

## 💡 Want More?

Let us know if you'd like to integrate:

- 📈 Monitoring with Prometheus & Grafana
- 🌿 Environment variables with .env support
- ⚙️ EC2 automation scripts for quick provisioning

Happy Deploying! 🚀
