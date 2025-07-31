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

## 🛠️ How to Build a Docker Image

1. Create a `Dockerfile`
2. Run:  
   ```bash
   docker build -t your-image-name .
