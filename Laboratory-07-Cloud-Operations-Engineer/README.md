# Laboratory 07: Cloud Operations Engineer

**Student:** Kylle Mariano  
**Course:** CCM101 – Cloud Computing  
**Mission:** Infrastructure Health and Container Monitoring

## 1. Mission Overview

For this mission, I took the role of a Cloud Operations Engineer responsible for checking server readiness before a website experiences increased traffic. The activity used Linux system utilities and Docker to inspect the host environment, run an Nginx web server, and investigate the results of simulated web requests.

The main purpose was to understand how system measurements, application logs, and container statistics help engineers assess infrastructure health and troubleshoot problems.

## 2. Objectives

- Establish a baseline of the Linux host's CPU, memory, and storage.
- Deploy an Nginx container using Docker.
- Send test HTTP requests to the website.
- Review access logs for successful responses and page errors.
- Observe container resource consumption.
- Document findings and organize screenshot evidence in GitHub.

## 3. Commands and Their Uses

| Command | Purpose |
|---|---|
| `cat /etc/os-release` | Identifies the operating system |
| `uname -r` | Displays the Linux kernel version |
| `lscpu` | Displays processor information |
| `free -h` | Checks RAM and swap usage |
| `df -h /` | Checks root filesystem capacity |
| `top` | Monitors running processes and CPU activity |
| `docker run -d --name client-website -p 8080:80 nginx` | Starts the Nginx container in the background |
| `docker ps` | Checks running containers |
| `curl http://localhost:8080` | Requests the Nginx welcome page |
| `curl -I http://localhost:8080` | Checks the HTTP response headers |
| `curl http://localhost:8080/hidden-admin-page` | Tests a missing page |
| `docker logs client-website` | Displays container logs |
| `docker stats` | Displays live container resource statistics |

## 4. Test Evidence and Results

The host inspection recorded memory and disk information for the Linux environment. The root filesystem had a reported capacity of 19 GB, with 13 GB available and 30% disk usage.

An Nginx container named `client-website` was configured to serve traffic through host port 8080. HTTP testing showed successful requests to the website and an unsuccessful request to `/hidden-admin-page`, which returned HTTP 404.

The container logs showed two successful HTTP 200 responses and one HTTP 404 response in the captured output. These results demonstrate how access logs can help distinguish successful requests from requests for unavailable pages.

Container resource measurements should also be recorded in `container-observability.md` after checking `docker stats`. The corresponding screenshots will be stored in the `screenshots/` folder.

## 5. Skills Developed

This mission provided practice in:

- Linux resource inspection and system administration.
- Docker container deployment and management.
- HTTP request testing with `curl`.
- Application log inspection and error identification.
- Container performance monitoring.
- Markdown documentation and GitHub portfolio management.

## 6. Conclusion

This laboratory demonstrated that a running web server should be checked at both the application and host levels. Examining system resources, verifying HTTP responses, reviewing logs, and monitoring container metrics helps engineers investigate errors and evaluate infrastructure health. These skills are useful for maintaining reliable cloud services.
