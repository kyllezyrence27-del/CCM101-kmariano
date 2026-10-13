# Docker and Application Monitoring

**Student:** Kylle Mariano  
**Course:** CCM101 – Cloud Computing  
**Laboratory:** 07 – Cloud Operations Engineer

## 1. Monitoring Overview

This report focuses on observing a web application running in a Docker container. The activity uses Nginx to serve HTTP requests and Docker tools to examine application activity and resource consumption.

## 2. Container Status

The container list will be checked to confirm whether Nginx is running and to inspect its configured ports. The deployment results will be documented after the container has been started and tested.

## 3. Website Request Tests

Test requests will be sent to the Nginx service using `curl`.

| Scenario | Purpose |
|---|---|
| Access the homepage | Verify normal website access |
| Request a missing page | Observe how the server handles a nonexistent resource |

The actual HTTP response codes and command outputs will be recorded after testing.

## 4. Log Analysis

The command `docker logs client-website` will be used to review the container's output. When access logging is enabled and configured normally, the entries can help show which pages were requested and how the server responded.

## 5. Resource Monitoring

Docker's live statistics will be inspected using `docker stats`. The monitoring process will focus on CPU utilization, memory usage, and network traffic while the web server is running.

## 6. Screenshot Evidence

Supporting screenshots will be organized in the `screenshots/` folder. The evidence will cover container deployment, simulated HTTP requests, application logs, and resource statistics.

## 7. Conclusion

Monitoring a container involves more than checking whether it is running. Reviewing HTTP responses, logs, and resource statistics provides a clearer picture of application behavior and helps identify issues that may need further investigation.

Verified measurements and observations will be added once the required tests have been completed.
