 Docker Notes

---

## What is Docker?

**Definition:**  
Docker is a containerization platform which allows us to **package an application with all dependencies** into an isolated environment called a **container**.

**Container:**  
Container is a **running instance of an image** which consists of **application + dependencies**.

---

### Problem without Docker

- “It works on my machine, but not on yours.”  
- “Application breaks when we move from development to production environment.”

**Solution:**  
- With Docker, we package everything inside a container to **ensure consistency across all environments**.  
- The application can run on **any system** without worrying about OS versions or library conflicts.

**Advantages:**  
- **Faster Deployments:** Containers start instantly compared to traditional VMs.  
- **Loose Coupling:** Multiple containers can run as **micro-services**.

---

## Docker Images

- Docker image is the **blueprint of an application**.  
- It contains **code + libraries + dependencies + tools** used in the application.  
- **Immutable:** Once built, you cannot change it. Create a new image for updates.  
- Images are stored in **Docker Hub** or private registry for reuse.

**Commands:**
```bash
docker build -t my-app .
docker images
docker push <repository-name>
Docker Containers
Basically, Docker container is a running instance of Docker images.

Docker containers are isolated, lightweight, and portable environments where the application runs.

Commands:

bash
Copy code
docker run -p 4000:4000 my-app
docker ps
docker stop <container-id>
docker rm <container-id>
Base Image in Docker
Base image is the starting point for building a Docker image.

A Dockerfile inherits from a base image using the keyword FROM.

Examples:

Node.js Application = base image node:lts

Python Application = base image python:3.11

Base images can be official/built-in.

Command in Dockerfile:

dockerfile
Copy code
FROM node:lts
Docker Volumes
Basically, volumes are a storage mechanism.

Key Points:

Data Persistence: We use volumes so that data remains even if the container is deleted.

Separate Storage: Stored separately from the container’s filesystem.

Live Sync: If we run a container with a volume, changes made in the local project directory automatically reflect inside the container.

Command Example:

bash
Copy code
docker run -v /local/path:/usr/src/app my-app
Docker Compose
Docker Compose is a tool for managing multiple containers easily.

Key Points:

YAML configuration files are used for defining multiple containers.

Reduces the complexity of complex Docker commands.

Used for large applications where we have multiple containers like backend, frontend, database, etc.

Minimal Example YAML:

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
Command to run all containers:

bash
Copy code
docker compose up
