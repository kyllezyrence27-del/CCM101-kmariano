# Docker Compose Deployment Guide

## Overview

Docker Compose makes it possible to organize and run several related containers as one application environment. For this laboratory, it is used to deploy Nextcloud together with MariaDB so that the application can store and manage its data through a separate database service.

## Prerequisites

Docker and Docker Compose should be installed and available before starting the deployment process.

## Deployment Procedure

The following commands were used to check the Docker environment, access the project repository, start the application stack, confirm the running services, test the Nextcloud application, inspect the services, and shut down the deployment:

```bash
docker --version
docker-compose version

git clone https://github.com/kyllezyrence27-del/CCM101-kmariano.git
cd CCM101-kmariano/Laboratory-06-Cloud-Deployment-Engineer

docker-compose up -d

docker-compose ps

curl -I http://localhost:8080

docker-compose logs

docker-compose down

docker-compose ps
```

Docker Compose version 1.29.2 was available in the working environment. The `docker-compose up -d` command was used to create and run the required application services in the background.

The services were checked using `docker-compose ps` to make sure that the Nextcloud and MariaDB containers were active. The application was configured to use port `8080` for browser access.

The Nextcloud service was tested using `curl -I http://localhost:8080`, which produced an `HTTP/1.1 200 OK` response. The application was also opened in a web browser through:

```text
http://localhost:8080
```

The Nextcloud setup page appeared successfully, confirming that the web application was accessible.

## Docker Compose Configuration

The application stack is composed of two main services. MariaDB is responsible for handling the application's database requirements, while Nextcloud provides the web-based application interface.

The MariaDB service is configured with:

```yaml
database:
  image: mariadb:10.6
```

The Nextcloud service is configured with:

```yaml
app:
  image: nextcloud
  ports:
    - 8080:80
```

The application communicates with the database through the Docker Compose network using `database` as the database host.

## Deployment Result

The completed deployment showed how an application and its database can operate as separate but connected containers. Nextcloud handled the user-facing web application, while MariaDB provided the data storage service. Docker Compose simplified the process by allowing both services to be controlled through one configuration.

## Conclusion

This laboratory gave me a better understanding of how containerized applications are deployed and managed. I learned how to verify Docker tools, start multiple services, check container status, test an application through an exposed port, inspect service logs, and properly stop the deployment. The activity also helped me understand the importance of communication between application and database containers in a cloud environment.
