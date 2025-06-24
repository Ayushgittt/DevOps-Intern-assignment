# DevOps-Intern-assignment

# 🚀 Microservices Reverse Proxy with Docker Compose
This project demonstrates how to containerize two services (written in Go and Python) and connect them using Nginx as a reverse proxy, all orchestrated via Docker Compose.
The goal of this assignment is to:

* Build dockerfile and docker compose file for Go and Python services
* Route traffic through Nginx reverse proxy

---

## 📁 Project Structure



            ├── docker-compose.yml
            ├── nginx
            |   └── nginx.conf
            │   └── Dockerfile
            ├── service_1
            │   └── Dockerfile
            ├── service_2
            │   └── Dockerfile
            └── README.md



---
## 🛠️ Setup Instructions

▶️ To Build & Run
Run the following command from the root directory:



    docker compose up --build




This will:
- Build service_1 (Go) and service_2 (Python)
- Build a custom Nginx image using nginx.conf
- Start all containers and set up internal networking



---


## 🌐 How Routing Works
Nginx acts as a reverse proxy listening on localhost:8080.

It is configured to:
- Forward http://localhost:8080/service1/ping → service1:8001/ping
- Forward http://localhost:8080/service2/hello → service2:8002/hello

Nginx routes from nginx.conf: Each route is explicitly defined for strict access control.

---

## 🏅 Bonus Features
✅ Multi-Stage Docker Build for service_2
service_2 (Python) uses a multi-stage Dockerfile, which:
- Installs dependencies in a temporary build stage
- Produces a smaller, production-ready runtime image
- Improves build caching and layer separation

Benefits:
- Smaller image size
- Faster builds
- Secure and clean production container


---
## Video Link for this Assignment

 https://drive.google.com/file/d/1KMDcp6fqKZdpM6HAK4ikbIWX4rNePEmP/view?usp=sharing






