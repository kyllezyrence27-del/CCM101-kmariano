# Laboratory 07: Cloud Operations Engineer

**Student:** Kylle Mariano  
**Course:** CCM101 – Cloud Computing  
**Mission:** Infrastructure Health and Container Monitoring

## 1. Mission Overview

For this mission, I will take the role of a Cloud Operations Engineer responsible for checking server readiness before a website experiences increased traffic. The activity uses Linux system utilities and Docker to examine the host environment, run an Nginx web server, and investigate the results of simulated web requests.

The main purpose is to understand how system measurements, application logs, and container statistics help engineers assess infrastructure health and troubleshoot problems.

## 2. Objectives

- Establish a baseline of the Linux host's CPU, memory, and storage.
- Run an Nginx container using Docker.
- Send test HTTP requests to the website.
- Review access logs for successful responses and page errors.
- Observe container resource consumption in real time.
- Present the findings through organized documentation and screenshots.

## 3. Commands and Their Uses

| Command | What it helps me examine |
|---|---|
| `lscpu` | Processor details and available CPU configuration |
| `free -h` | RAM and swap capacity |
| `df -h /` | Available disk space on the root filesystem |
| `top` | Active processes and CPU utilization |
| `docker ps` | Container status and port mappings |
| `docker logs client-website` | Requests recorded by the web server |
| `docker stats` | Container CPU, memory, and network statistics |
| `curl` | HTTP responses from the deployed website |

## 4. Test Evidence

I will attach the screenshots captured during the host inspection, Nginx deployment, HTTP traffic simulation, log inspection, and resource monitoring checkpoints. Actual values and observations will be recorded after each test is completed.

## 5. Skills Developed

This mission provides practice in Linux resource inspection, container management, HTTP request testing, troubleshooting with logs, Docker monitoring, technical writing, and maintaining a cloud computing portfolio.

## 6. Conclusion

A running web server does not automatically mean that an application is healthy. Engineers also need to check the underlying system resources, verify HTTP responses, and review the logs to understand what happens during normal and unsuccessful requests.

The evidence gathered throughout this activity will be used to evaluate the test environment and explain how monitoring supports reliable infrastructure operations.
