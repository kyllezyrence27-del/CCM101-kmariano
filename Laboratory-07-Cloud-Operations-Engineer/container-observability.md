# Docker and Application Monitoring

**Student:** Kylle Zyrene Mariano  
**Course:** CCM101 – Cloud Computing  
**Laboratory:** 07 – Cloud Operations Engineer

## 1. Introduction

This report describes the deployment and monitoring of an Nginx web server using Docker. The activity involves checking the running container, sending HTTP requests, examining application logs, and observing resource consumption.

## 2. Deploying the Nginx Container

The Nginx image was used to create a container named `client-website`. The container runs in the background, with host port 8080 mapped to container port 80.

Command used:

```bash
docker run -d --name client-website -p 8080:80 nginx
```

The following command can be used to verify that the container is running:

```bash
docker ps
```

The website can be accessed locally through `http://localhost:8080`.

## 3. Testing HTTP Requests

### Successful Website Request

The following command requests the Nginx welcome page:

```bash
curl http://localhost:8080
```

The server returns the HTML content of the welcome page when the request succeeds.

A header-only request can also be performed:

```bash
curl -I http://localhost:8080
```

The observed response was HTTP 200, which indicates that the request was successful.

### Testing a Missing Page

The following command requests a page that does not exist:

```bash
curl http://localhost:8080/hidden-admin-page
```

The server returned HTTP 404 because the requested page was not found. This test demonstrates how a web server responds when a visitor requests an unavailable resource.

## 4. Reviewing Application Logs

The Nginx logs can be viewed using:

```bash
docker logs client-website
```

The observed logs contained two successful HTTP 200 responses and one failed HTTP 404 response. The failed request was associated with `/hidden-admin-page`.

### Example of the HTTP 404 Log Entry

```text
172.17.0.1 - - [13/Oct/2026:07:25:06 +0000] "GET /hidden-admin-page HTTP/1.1" 404 153 "-" "curl/8.5.0" "-"
```

Application logs help engineers understand the events that occur inside a service. They can reveal failed requests and other errors, making it easier to investigate problems and determine what may have caused them.

## 5. Monitoring Container Resources

Docker provides the `docker stats` command for observing resource usage while a container is running.

```bash
docker stats
```

The output includes CPU percentage, memory usage, memory limits, and Network I/O. These measurements help show how much of the host's resources the container is consuming.

The actual CPU percentage, memory usage, and Network I/O values will be recorded after the monitoring command is executed and a screenshot is captured.

## 6. Evidence and Screenshots

The following evidence will be stored in the `screenshots/` folder:

| Filename | Description |
|---|---|
| `memory-check.png` | Host RAM and swap information |
| `disk-check.png` | Root filesystem capacity and available space |
| `install-nginx.png` | Nginx container deployment |
| `simulation1.png` | Successful HTTP request |
| `simulation2.png` | Missing-page request returning HTTP 404 |
| `docker-logs.png` | Application logs showing HTTP responses |
| `container-metrics.png` | Live container resource measurements |

## 7. Conclusion

This laboratory activity provided practical experience in deploying a containerized web server, testing HTTP requests, and reviewing application logs. It also introduced Docker's resource monitoring capabilities. Using both logs and metrics helps engineers investigate application errors and evaluate the performance of containerized services.
