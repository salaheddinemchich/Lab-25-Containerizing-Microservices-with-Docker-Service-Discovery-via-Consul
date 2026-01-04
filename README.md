# Microservices Project with Docker

This project demonstrates a microservices architecture using Spring Boot, Docker, and Consul.

## Services

*   **Client Service**: Manages clients (Port 8088)
*   **Voiture Service**: Manages cars (Port 8089)
*   **Gateway Service**: Entry point for the architecture (Port 8888)
*   **Consul**: Service Discovery (Port 8500)
*   **MySQL**: Database (Port 3307 on host)
*   **phpMyAdmin**: Database interface (Port 8083 on host)

## Prerequisites

*   Docker & Docker Compose
*   Java 17 (if running locally without Docker)
*   Maven 3.8+ (if running locally)

## How to Run

1.  **Build and Start**:
    Run the following command in the root directory:
    ```bash
    docker compose up -d --build
    ```
    ![alt text](image.png)

2.  **Check Status**:
    Verify that all containers are running:
    ```bash
    docker compose ps
    ```

3.  **Logs**:
    To see logs for a specific service (e.g., client-service):
    ```bash
    docker compose logs -f client-service
    ```

## Access Points

*   **Consul Dashboard**: [http://localhost:8500](http://localhost:8500)

*   **phpMyAdmin**: [http://localhost:8083](http://localhost:8083) (User: `root`, Password: `root`)

*   **Gateway API**: [http://localhost:8888](http://localhost:8888)
*   **Client Service**: [http://localhost:8088](http://localhost:8088)
*   **Voiture Service**: [http://localhost:8089](http://localhost:8089)
<img width="1804" height="788" alt="image-1" src="https://github.com/user-attachments/assets/c792deee-96a6-4361-8aa6-8d7a2a39a495" />
<img width="1800" height="888" alt="image-2" src="https://github.com/user-attachments/assets/529341c0-fa20-47a6-b5a2-59d3c8eda22f" />

## Troubleshooting

*   **Ports Occupied**: If ports 3306 or 8080/81/82 are busy, the `docker-compose.yml` is configured to use host ports **3307** (MySQL) and **8083** (phpMyAdmin).
*   **Service Registration**: It may take a minute for services to register with Consul. Check the logs if they don't appear immediately.
