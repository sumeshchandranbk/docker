# Docker Overview

Docker is an open platform that helps you build, ship, and run applications efficiently. It separates your applications from the underlying infrastructure, enabling faster development cycles and consistent deployments across environments. By adopting Docker’s approach to packaging, testing, and distributing software, teams can significantly reduce the time between writing code and running it in production.

---

## 🚀 The Docker Platform

Docker packages applications into **containers**—lightweight, isolated environments that include everything required to run your software. Because containers are self‑contained, they behave consistently across:

- Developer laptops
- On‑premises servers
- Cloud platforms
- Hybrid environments

Docker provides tooling to manage the full container lifecycle:

- Develop applications and dependencies inside containers
- Use containers as the unit of distribution and testing
- Deploy containers directly to production or orchestrate them as services

---

## What You Can Use Docker For

### ⚡ Fast and Consistent Delivery

Docker standardizes development environments, making it ideal for CI/CD workflows.

A typical workflow:

- Developers build and share containerized applications.
- Containers are pushed to test environments for automated or manual testing.
- Bugs are fixed locally and redeployed for validation.
- Once approved, updated images are pushed to production.

### 📈 Scalable and Responsive Deployments

Docker containers are portable and lightweight, enabling dynamic scaling. They run consistently across:

- Local machines
- Virtual or physical servers
- Cloud providers
- Mixed or hybrid environments

### 💡 Efficient Resource Utilization

Containers consume fewer resources than traditional virtual machines, allowing more workloads to run on the same hardware. This makes Docker ideal for high‑density or cost‑sensitive environments.

---

## Docker Architecture

![alt text](docker-architecture.jpg)

Docker uses a **client–server architecture**:

- The **Docker client** sends commands.
- The **Docker daemon** builds, runs, and manages containers.
- Communication happens via a REST API over UNIX sockets or a network interface.
- **Docker Compose** provides a higher‑level interface for multi‑container applications.

### Docker Daemon (`dockerd`)

The daemon listens for API requests and manages Docker objects such as images, containers, networks, and volumes. It can also coordinate with other daemons to manage services.

### Docker Client (`docker`)

The CLI is the primary interface for most users. Commands like `docker run` or `docker build` are sent to the daemon for execution. A single client can communicate with multiple daemons.

### Docker Desktop

Docker Desktop bundles everything needed for container development on Windows, macOS, or Linux, including:

- Docker Engine
- Docker CLI
- Docker Compose
- Kubernetes
- Credential helpers
- Docker Content Trust

### Docker Registries

A registry stores Docker images. Docker Hub is the default public registry, but private registries are also supported.

- `docker pull` retrieves images
- `docker push` uploads images

---

## Docker Objects

### Images

An image is a read‑only template used to create containers. Images often extend other images (e.g., Ubuntu + Apache + your app).  
Images are defined using a **Dockerfile**, where each instruction creates a new layer. Only changed layers are rebuilt, keeping images lightweight and fast.

### Containers

A container is a runnable instance of an image. You can start, stop, move, or delete containers using the CLI or API. Containers can be connected to networks, assigned storage, or used to create new images.

Containers are isolated from each other and from the host, but the level of isolation is configurable.

#### Example: Running a Container

```bash
docker run -it ubuntu /bin/bash