# Docker and Application Monitoring

**Student:** Kylle Mariano  
**Course:** CCM101 – Cloud Computing  
**Laboratory:** 07 – Cloud Operations Engineer

## 1. Introduction

This report documents the deployment and monitoring of an Nginx web server using Docker. The activity involved checking the running container, sending HTTP requests, examining application logs, and observing resource consumption.

## 2. Deploying the Nginx Container

The Nginx image was used to create a container named `client-website`. The container runs in the background, with host port 8080 mapped to container port 80.

Command used:

```bash
docker run -d --name client-website -p 8080:80 nginx
```

To verify that the container is running, the following command was used:

```bash
docker ps
```

The website was accessed locally through `http://localhost:8080`.

## 3. Testing HTTP Requests

### Successful Website Request

The following command requests the Nginx welcome page:

```bash
curl http://localhost:8080
```

The server returned the HTML content of the welcome page.

A header-only request was also performed:

```bash
curl -I http://localhost:8080
```

The observed response was HTTP 200, indicating that the request was successful.

### Testing a Missing Page

The following command requests a page that does not exist:

```bash
curl http://localhost:8080/hidden-admin-page
```

The server returned HTTP 404 because the requested page was not found.

## 4. Reviewing Application Logs

The container logs were inspected using:

```bash
docker logs client-website
```

The captured output showed two successful HTTP 200 responses and one failed HTTP 404 response.

### Example of the HTTP 404 Log Entry

```text
172.17.0.1 - - [13/Oct/2026:08:19:00 +0000] "GET /hidden-admin-page HTTP/1.1" 404 153 "-" "curl/8.5.0" "-"
```

Application logs help engineers investigate failed requests and understand application behavior. The recorded request path, response code, and timestamp provide useful evidence when troubleshooting website problems.

## 5. Monitoring Container Resources

Docker's `docker stats` command was used to observe the resource consumption of the running container.

Command used:

```bash
docker stats
```

### Actual Metrics Observed

| Metric | Observed Value |
|---|---|
| Container name | `client-website` |
| CPU usage | 0.00% |
| Memory usage | 2.73 MiB |
| Memory limit | 1.859 GiB |
| Memory usage percentage | 0.14% |
| Network I/O | 3.23 kB received / 2.86 kB sent |
| Block I/O | 0 B read / 12.3 kB written |
| PIDs | 2 |

### Analysis

At the time of measurement, the container used 0.00% CPU and 2.73 MiB of memory, equivalent to 0.14% of its displayed memory limit. Network I/O was 3.23 kB received and 2.86 kB sent.

These readings indicate low resource consumption during the observation. However, the values may change as the container handles additional requests or workload.

## 6. Evidence and Screenshots

The following screenshots should be stored in the `screenshots/` folder:

| Filename | Description |
|---|---|
| `memory-check.png` | Host RAM and swap information |
| `disk-check.png` | Root filesystem capacity and available space |
| `install-nginx.png` | Nginx container deployment |
| `simulation1.png` | Successful HTTP request |
| `simulation2.png` | Missing-page request returning HTTP 404 |
| `docker-logs.png` | Application logs showing HTTP responses |
| `container-metrics.png` | Docker resource metrics |

## 7. Conclusion

This laboratory provided practical experience in deploying an Nginx container, testing HTTP requests, examining application logs, and monitoring resource consumption. Logs help explain individual events, while metrics provide numerical information about container performance. Together, these tools help engineers troubleshoot problems and assess the health of containerized services.
