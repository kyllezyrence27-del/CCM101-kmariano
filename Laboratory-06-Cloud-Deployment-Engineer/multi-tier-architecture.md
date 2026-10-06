# Multi-Tier Architecture

## What is a Two-Tier Architecture?

A two-tier architecture separates an application into two connected layers. The first layer handles the application and user requests, while the second layer manages the data needed by the application. This structure allows each component to focus on its specific function.

## Web/Application Tier

The web or application tier provides the service that users interact with. For this laboratory, Nextcloud acts as the application tier. It receives requests through the web browser, processes them, and communicates with the database service whenever application information is needed.

## Database Tier

The database tier handles the storage and organization of persistent application data. MariaDB is used as the database service in this activity. It stores information needed by Nextcloud, including user-related data and application records.

## Why Separate the Tiers?

Keeping the application and database in separate containers improves the organization of the system. Each service can be managed independently, making maintenance and troubleshooting easier. This approach also follows the principle of giving each component a specific responsibility while allowing the services to communicate with one another.
