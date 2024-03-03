# Docker Compose Setup Guide for NiFi and MarkLogic

This guide provides detailed instructions for using Docker Compose to orchestrate Apache NiFi and MarkLogic services within the BNSF MarkLogic Project. The process involves setting up, configuring, and managing these services to ensure seamless data processing and integration.

## Prerequisites

Before proceeding, ensure you have the following installed on your system:

- Docker
- Docker Compose

It is also recommended to have a basic understanding of Docker concepts such as images, containers, and Docker Compose files.

## Setup and Configuration

### 1. Clone the Repository

First, clone the BNSF MarkLogic Project repository to your local environment if you haven't already:

```bash
git clone <repository-url>
```

Navigate to the project's root directory:

```bash
cd bnsfML
```

### 2. Understanding the `docker-compose.yml` File

The `docker-compose.yml` file in the project root defines the multi-container setup for NiFi and MarkLogic. Familiarize yourself with its structure, noting how services are defined, including image sources, environment variables, port mappings, and volume mounts.

### 3. Customizing Configuration

Before starting the services, you may need to customize the configuration to match your environment. This includes setting environment variables for NiFi and MarkLogic, such as hostnames, default usernames, and passwords.

### 4. Starting the Services

With the `docker-compose.yml` file configured, start the services using the following command:

```bash
docker-compose up -d
```

This command will download the necessary images and create containers in detached mode.

### 5. Verifying the Services

Verify that the NiFi and MarkLogic services are running by checking the list of active Docker containers:

```bash
docker ps
```

You should see containers for NiFi and each MarkLogic instance listed.

## Accessing the Web Interfaces

- **NiFi**: Access the NiFi web interface by navigating to `https://localhost:8443/nifi` in your web browser. The default login credentials are specified in the Dockerfile and docker-compose.yml.
- **MarkLogic**: Access the MarkLogic Admin Interface by navigating to `http://localhost:8001` for the first MarkLogic instance. Default login credentials are set in the docker-compose.yml file.

## Managing Services

Learn basic `docker-compose` commands to manage your services:

- **Start services**: `docker-compose up -d`
- **Stop services**: `docker-compose down`
- **View logs**: `docker-compose logs`

## Troubleshooting

Encountered issues? Check the Docker and service logs for error messages. Common issues may include port conflicts, insufficient permissions, or environment variable misconfigurations.

## Conclusion

You have now successfully set up and configured Apache NiFi and MarkLogic using Docker Compose. This setup provides a robust environment for data processing and integration tasks within the BNSF MarkLogic Project.

For further customization and advanced configurations, refer to the official Docker, NiFi, and MarkLogic documentation.
