# Docker Overview

This document provides a brief overview of Docker and its key concepts, especially for those starting with containerization and DevOps.

---

## 📦 What is Docker?

Docker is an open-source platform used to automate the deployment, scaling, and management of applications inside lightweight, portable containers.

---

## ❓ Why Docker?

- Eliminates the "it works on my machine" problem
- Enables faster and consistent deployments
- Simplifies app lifecycle management
- Supports CI/CD pipelines

---

## 🔧 Use of Docker

- Developing and testing applications
- Microservices deployment
- Automating CI/CD pipelines
- Ensuring consistency across environments
- Running legacy applications

---

## 🧠 Core Concepts

### ✅ What is a Container?

A container is a lightweight, standalone, and executable package that includes everything needed to run a piece of software — code, runtime, libraries, and dependencies.

### 📦 What is Containerization?

Containerization is the process of encapsulating an application and its dependencies into a container image, ensuring consistency across environments.

### 📄 What is a Dockerfile?

A Dockerfile is a text file with a set of instructions to build a Docker image (e.g., installing software, copying files, setting environment variables).

### 🖼️ What is a Docker Image?

A Docker image is a read-only template used to create containers. It includes the app code, libraries, environment variables, and configuration files.

### 📦 What is a Docker Container?

A Docker container is a running instance of a Docker image. Containers are isolated but share the host system’s kernel.

### 📚 What is a Docker Registry?

A Docker registry is a storage and distribution system for Docker images. It allows users to push and pull images.

### 🌐 What is Docker Hub?

Docker Hub is the default public registry where users can publish and share container images.

---

## ⚙️ How Docker Works

Docker uses a client-server architecture:
- The **Docker Client** communicates with the **Docker Daemon** (engine).
- The daemon builds, runs, and manages containers.
- Images are fetched from a registry like Docker Hub.

---

## 🧱 Container vs Virtual Machine

| Feature          | Container               | Virtual Machine        |
|------------------|-------------------------|------------------------|
| Boot time        | Seconds                 | Minutes                |
| Size             | Lightweight (MBs)       | Heavyweight (GBs)      |
| Isolation        | Process-level           | Full OS-level          |
| Performance      | Near-native             | Slight overhead        |
| Resource usage   | Efficient               | More resource-intensive|

---

## Docker Command Overview

## 🔹 1. `docker build`

👉 Used to build a Docker image from a **Dockerfile**.\
- Reads instructions from `Dockerfile` and creates a container image.\
- You can tag the image with `-t`.

**Example:**

``` bash
docker build -t myapp:1.0 .
```

➡️ Builds an image named `myapp` with tag `1.0` from the current
directory (`.`).

------------------------------------------------------------------------

## 🔹 2. `docker images`

👉 Lists all the images available on your system.\
- Shows repository, tag, image ID, created time, and size.

**Example:**

``` bash
docker images
```

➡️ You'll see something like:

    REPOSITORY   TAG   IMAGE ID       CREATED        SIZE
    myapp        1.0   d9e6b21e10bc   2 minutes ago  132MB

------------------------------------------------------------------------

## 🔹 3. `docker ps`

👉 Lists **running containers**.\
- Use `-a` to see all containers (running + stopped).

**Example:**

``` bash
docker ps
docker ps -a
```

➡️ Output shows container ID, image, command, status, ports, and names.

------------------------------------------------------------------------

## 🔹 4. `docker network`

👉 Manages **networks** for communication between containers.\
- Types: `bridge` (default), `host`, `overlay`.\
- Useful for multi-container setups.

**Examples:**

``` bash
docker network ls            # list networks
docker network create mynet  # create custom network
docker network inspect mynet # see details
docker network connect mynet mycontainer
```

------------------------------------------------------------------------

## 🔹 5. `docker volume`

👉 Manages **persistent storage** for containers.\
- Volumes store data outside the container's lifecycle.\
- Containers can share volumes.

**Examples:**

``` bash
docker volume ls                # list volumes
docker volume create myvol      # create volume
docker run -v myvol:/data ...   # mount volume
docker volume inspect myvol     # check details
```

------------------------------------------------------------------------

## 🔹 6. `docker scout`

👉 Newer Docker tool (security + analysis).\
- Scans images for **vulnerabilities** and gives recommendations.\
- Helps improve supply chain security.

**Example:**

``` bash
docker scout quickview myapp:1.0
```

➡️ Shows vulnerabilities, outdated packages, and fixes.

------------------------------------------------------------------------

## 🔹 7. `docker init`

👉 Creates a **starter Docker setup** for your project.\
- Detects project type (Node, Python, Java, etc.).\
- Generates: - `Dockerfile` - `.dockerignore` - `compose.yaml`

**Example:**

``` bash
docker init
```

➡️ Walks you through prompts like language, port, and dependencies.

------------------------------------------------------------------------

