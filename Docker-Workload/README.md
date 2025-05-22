# 🗳️ Voting App - Dockerized Microservices

This repository contains a simple microservices-based voting application using Docker. It includes services for voting, result display, background processing, Redis, and PostgreSQL. This app is a great way to learn about Docker Compose, Docker Swarm, and container healthchecks.

---

## 📁 Project Structure

```bash
.
├── docker-compose.yml              # For local or public single-node Docker setup
├── docker-compose.images.yml       # To build app images locally from source
├── healthchecks/
│   ├── redis.sh                    # Healthcheck script for Redis
│   └── postgres.sh                 # Healthcheck script for PostgreSQL
├── vote/                           # Python Flask voting frontend
├── result/                         # Node.js result backend
├── worker/                         # .NET background processor
