# 🔁 Nginx Reverse Proxy with Docker Compose

This project sets up a reverse proxy using **Nginx** and **Docker Compose** to route traffic to two microservices:

- 🐍 A Python application
- 🦫 A Golang application

The Nginx container handles incoming HTTP requests and routes them based on the path prefix (`/service1`, `/service2`).

---

## 📁 Project Structure

project-root/

│ 

├── docker-compose.yml 

├── nginx/ 

│ ├── nginx.conf

│ └── Dockerfile 

├── service_1/ ← Golang app │ 

   └── Dockerfile 
   
├── service_2/ ← Python app │ 

   └── Dockerfile 
   
└── README.md


---

## 🚀 Setup & Execution

### Prerequisites

  Installations:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- [Git](https://git-scm.com/)

### Steps to Run

1. Clone this repository:
   
      git clone https://github.com/your-username/your-repo-name.git
   
      cd your-repo-name
   
2. Build and start all services:

      docker-compose up --build

3. Access services via your browser:

      http://localhost:8080/service1

      http://localhost:8080/service2

### ⚙️ How It Works

. Nginx listens on port 8080 and routes:

      /service1 → Golang service

      /service2 → Python service

. Each service runs in its own isolated container, using bridge networking.

. Nginx logs incoming requests with timestamps and routes.


### 🩺 Health Checks

Both services are configured with basic health checks using curl to ensure availability and reliability during runtime.


### 🔍 Logs

Check access logs for requests routed through Nginx:

docker-compose exec nginx cat /var/log/nginx/access.log

