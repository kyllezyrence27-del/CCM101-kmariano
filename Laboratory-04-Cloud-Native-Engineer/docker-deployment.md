# Docker Deployment and Container Lifecycle

## Introduction

This document records the Docker commands performed during Laboratory Activity 4. The main purpose of the activity was to explore Docker, deploy an Nginx web server, and understand how containers can be managed through different lifecycle operations.

## Docker Commands Executed

### 1. Verify Docker Installation

```bash
docker --version
```

This command checks whether Docker is installed and displays its current version.

### 2. Check Docker Environment

```bash
docker info
```

This command shows detailed information about the Docker engine and its operating environment.

### 3. Pull the Nginx Image

```bash
docker pull nginx
```

This command retrieves the Nginx image from Docker Hub and makes it available for container deployment.

### 4. Create and Run a Container

```bash
docker run -d --name nginx-server -p 8080:80 nginx
```

This command starts an Nginx container in the background and maps the host port 8080 to the container's port 80.

### 5. List Active Containers

```bash
docker ps
```

This command lists all currently running containers and provides information such as their names, images, and status.

### 6. Verify the Nginx Server

```bash
curl http://localhost:8080
```

This command tests the web server locally. Receiving the Nginx HTML page indicates that the container is operating properly.

### 7. Stop the Container

```bash
docker stop nginx-server
```

This command stops the running container without deleting it.

### 8. View All Containers

```bash
docker ps -a
```

This command displays both active and inactive containers, including their current statuses.

### 9. Restart the Container

```bash
docker start nginx-server
```

This command starts the stopped Nginx container again.

## Container Lifecycle Summary

The activity demonstrated the basic lifecycle of a Docker container. A container can be created, started, stopped, checked, and restarted depending on the requirements of the application or administrator.

## Evidence

The screenshots folder contains the captured terminal outputs used as evidence for the Docker commands performed during this laboratory activity.
