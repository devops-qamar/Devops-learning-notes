# Docker Notes

---

## 1. What is Docker?

**Definition:**  
Docker is a containerization platform which allows us to **package an application with all dependencies** into an isolated environment called a **container**.

**Container:**  
A container is a **running instance of an image** which consists of **application + dependencies**.

---

### Problem without Docker

- “It works on my machine, but not on yours.”  
- “Application breaks when we move from development to production environment.”

### Solution

- With the help of Docker, we package everything inside a **container** to ensure consistency across all environments.  
- When packaged in a container, the application runs on **any system** without worrying about OS version or library conflicts.

### Advantages

- **Faster Deployments:** Containers start instantly compared to traditional VMs.  
- **Loose Coupling:** Multiple containers can run as **micro-services**.

---

## 2. Docker Images

**Definition:**  
Docker image is the **blueprint of an application**. It contains:

- Application code  
- Libraries  
- Dependencies / versions  
- Tools used in the application  

**Key Points:**  

- **Immutable:** Once built, images cannot be updated. Create a new image for updates.  
- Stored in **Docker Hub** or private registry for reuse.

**Commands:**  
```bash
# Build a Docker image from Dockerfile
docker build -t my-app .

# List all Docker images
docker images

# Push image to Docker Hub
docker push
## 3. Docker Containers

**Definition:**  
Docker container is a **running instance of a Docker image**.

**Key Points:**  

- **Isolated**, **lightweight**, and portable environments  
- The application runs inside these containers  

**Commands:**  
```bash
# Run a container
docker run -p 4000:4000 my-app

# List running containers
docker ps

# Stop a container
docker stop <container-id>

# Remove a container
docker rm <container-id>

4. Base Image in Docker
Definition:
Base image is the starting point for building a Docker image. A Dockerfile inherits from a base image using the FROM keyword.

Examples:

Node.js Application → FROM node:lts

Python Application → FROM python:3.11

Base images can be official/built-in.

Command in Dockerfile:

dockerfile
Copy code
FROM node:lts
5. Docker Volumes
Definition:
Docker volumes are a storage mechanism to save data outside the container.

Key Points:

Data Persistence: Data remains even if the container is deleted.

Separate Storage: Stored separately from the container's filesystem.

Live Sync: Changes made in the local project directory automatically reflect inside the container.

Command Example:

bash
Copy code
# Mount local folder into container
docker run -v /home/qamar/Desktop/nodeApp:/usr/src/app my-app
6. Docker Compose
Definition:
Docker Compose is a tool for managing multiple containers easily using a YAML file.

Key Points:

YAML configuration files define multiple containers

Reduces complexity of multiple docker run commands

Used for large applications with multiple services (backend, frontend, database, etc.)

Minimal Example YAML (docker-compose.yml):

yaml
Copy code
services:
  web:
    build: .
    container_name: my-container
    ports:
      - "4000:4000"
  db:
    image: mongo
Commands:

bash
Copy code
# Start all services defined in docker-compose.yml
docker compose up

# Stop all services
docker compose down

# View logs
docker compose logs
