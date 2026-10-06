# Mission Reflection

## What I Learned

This laboratory taught me how containerized services can be combined to create a working cloud application. I learned that Nextcloud can function as the application service while MariaDB handles the database requirements. Although they run in separate containers, the services can communicate through the Docker Compose network.

I also learned that Docker Compose makes deployment more organized because the services and their configurations can be placed in one `docker-compose.yml` file. This allows multiple containers to be started, checked, and stopped using simple commands.

## Challenges Encountered

One challenge I experienced was understanding how the different containers work together. I had to verify that both the Nextcloud and MariaDB services were running correctly before accessing the application. Checking the containers with `docker-compose ps` helped me identify whether the deployment was successful.

Another challenge was testing the application through port `8080`. Using the `curl` command and opening the application in a browser helped me confirm that Nextcloud was responding properly.

## Skills Gained

This laboratory helped me develop practical skills in Docker Compose, container deployment, service monitoring, multi-tier architecture, and basic troubleshooting. I also became more comfortable with using terminal commands to start services, check their status, view logs, test an application, and stop containers.

## Reflection

The activity helped me understand that cloud deployment involves more than simply running an application. Different services must be properly configured and connected so that they can work together. Using Nextcloud and MariaDB allowed me to see how an application and database can be separated into individual containers while still functioning as one system.

Overall, I found the laboratory useful because it gave me hands-on experience with containerized cloud infrastructure. The knowledge I gained from this activity can be applied to future projects that require web applications, databases, Docker containers, and other cloud technologies.
