# Docker Notes


---

## What is Docker?

**Definition:**  
Docker is a containerization platform that allows us to package an application along with all its dependencies into an isolated environment called a **container**.

---

## Container

A **container** is a running instance of a Docker image.

It consists of:
- Application
- Dependencies
- Required libraries

---

## Problems Without Docker

- “It works on my machine but not on yours”
- Application breaks when moving from development to production environment

---

## Solution Using Docker

With Docker, we package everything inside a container to ensure **consistency across all environments**.

When an application is packaged inside a container, it can run on any system **without worrying about OS version or library conflicts**.

---

## Faster Deployments

Deployments become faster because:
- Containers start instantly
- Faster compared to traditional Virtual Machines (VMs)

---

## Loose Coupling (Microservices)

We achieve **loose coupling** by running multiple containers as **microservices**, where each service runs independently.

---

## Docker Images

A **Docker image** is the blueprint of an application.

It contains:
- Application code
- Libraries
- Dependencies
- Versions
- Tools required to run the application

**Key Points:**
- Docker images are **immutable**
- Once an image is built, it cannot be changed
- For updates, a **new image** is created
- Images are stored in **Docker Hub** or **private registries**

---

## Docker Containers

A **Docker container** is a running instance of a Docker image.

**Characteristics:**
- Lightweight
- Isolated
- Portable
- Provides an environment where the application runs

---

## Base Image in Docker

A **base image** is the starting point for building a Docker image.

In a Dockerfile, we inherit from a base image using the **FROM** keyword.

**Examples:**
- Node.js application → `node` base image
- Python application → `python` base image

Base images can be **official Docker images**.

---

## Docker Volumes

Docker volumes are used as a **storage mechanism**.

**Why we use volumes:**
- Data persists even if the container is deleted
- Stored separately from the container filesystem
- Changes in the local project directory automatically reflect inside the container

---

## Docker Compose

Docker Compose is a tool used to manage **multiple containers easily**.

**Key Features:**
- Uses `docker-compose.yml` file
- Defines multiple containers/services
- Reduces complexity of long Docker commands
- Used for large applications (backend, database, frontend, etc.)

---
