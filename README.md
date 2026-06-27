Microservices Docker Setup (Node.js + Docker + Compose)

Git repo link: https://github.com/bketanv41-droid/Microservices-Task.git

Project Overview

This project contains a simple microservices architecture built using Node.js and containerized using Docker.
It includes the following services:

-User Service (Port 3000)
-Product Service (Port 3001)
-Order Service (Port 3002)
-Gateway Service (Port 3003)

All services are orchestrated using Docker Compose.

- Prerequisites

Make sure you have installed:

Docker → https://www.docker.com/
Docker Compose
Node.js (optional for local testing)

-Setup Instructions
1. Clone the Repository
git clone <your-forked-repo-url>
cd submission

2. Build and Run All Services

Run the following command from the root folder (where docker-compose.yml is located):

docker compose up --build

This will:

Build all Docker images
Create containers
Start all microservices

3. Verify Running Containers
docker compose ps

You should see all services in Up state.

- Service Endpoints
Service	URL
User Service	http://localhost:3000
Product Service	http://localhost:3001
Order Service	http://localhost:3002
Gateway Service	http://localhost:3003


- Basic Troubleshooting
Containers not starting
docker compose logs

Check for:

missing dependencies
wrong start script
port conflicts
Port already in use

Change ports in docker-compose.yml:

ports:
  - "3000:3000"
  - Build issues

Rebuild cleanly:

docker compose down --remove-orphans
docker compose up --build
Service not reachable

Ensure:

container is running (docker ps)
correct port mapping
service is listening on 0.0.0.0, not localhost


📂 Final Project Structure
submission/
├── user-service/
│   └── Dockerfile
├── product-service/
│   └── Dockerfile
├── order-service/
│   └── Dockerfile
├── gateway-service/
│   └── Dockerfile
├── docker-compose.yml
└── README.md