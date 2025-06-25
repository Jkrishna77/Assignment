# DevOps Intern Assignment – Nginx Reverse Proxy + Docker

## Setup

1. Make sure Docker and Docker Compose are installed.
2. Clone this repository:
   ```sh
   git clone https://github.com/Jkrishna77/Assignment.git
   cd Assignment
Run:

docker compose up --build

OR:

Quick Start (One-Liner)
You can also start the stack directly using the compose file from GitHub, no clone needed:

docker compose -f https://raw.githubusercontent.com/Jkrishna77/Assignment/main/docker-compose.yml up --build

Note:
If you are on Windows, download the file first:

curl -O https://raw.githubusercontent.com/Jkrishna77/Assignment/main/docker-compose.yml

docker compose up --build

4. Access the services at:
- [http://localhost:8080/service1/ping](http://localhost:8080/service1/ping)
- [http://localhost:8080/service1/hello](http://localhost:8080/service1/hello)
- [http://localhost:8080/service2/ping](http://localhost:8080/service2/ping)
- [http://localhost:8080/service2/hello](http://localhost:8080/service2/hello)


---

## How Routing Works

- Nginx listens on port 8080.
- Requests to `/service1/*` go to the Go backend on port 8001.
- Requests to `/service2/*` go to the Python Flask backend on port 8002.
- Nginx acts as a reverse proxy, forwarding paths based on the prefix.

---

## Bonus Features

- Healthcheck enabled for service_2 (Flask) to ensure it’s running before Nginx starts.
- Nginx logs all incoming requests with timestamp and request path (combined log format).
- Uses Docker Compose with override for local port mapping (8080:80).
- Minimal, production-like Docker images for both services.

---

## Notes

- All networking is isolated via Docker bridge network.
- All containers (including Nginx) run in Docker—nothing runs on the host directly.
