[Back to Main README.md file](../../README.md)

# Docker Compose Setup Guide for NiFi and MarkLogic

This guide provides detailed instructions for using Docker Compose to orchestrate Apache NiFi and MarkLogic services within the BNSF MarkLogic Project. The process involves setting up, configuring, and managing these services to ensure seamless data processing and integration.

## Prerequisites

Before you begin, ensure the following prerequisites are met:

- Docker and Docker Compose are installed on your system.
- You have a basic understanding of Docker concepts such as images, containers, and Docker Compose files.
- The BNSF MarkLogic Project repository has been cloned to your local environment. Refer to the [Git-Setup-Guide.md](Git-Setup-Guide.md) for instructions on cloning the repository.

## Setup and Configuration

### Understanding the `docker-compose.yml` File

The `docker-compose.yml` file at the root of the project defines the multi-container setup for NiFi and MarkLogic. Familiarize yourself with its structure, paying close attention to how services are defined, including image sources, environment variables, port mappings, and volume mounts.

### Customizing Configuration

Customize the configuration to match your environment before starting the services. This may involve setting environment variables for NiFi and MarkLogic, such as hostnames, default usernames, and passwords.

### Starting the Services

Start the services with the configured `docker-compose.yml` file using the following command:

```bash
docker-compose up -d
```

This command downloads the necessary images and creates containers in detached mode.

### Verifying the Services

Check the list of active Docker containers to verify that the NiFi and MarkLogic services are running:

```bash
docker ps
```

You should see containers listed for NiFi and each MarkLogic instance.

## Accessing the Web Interfaces

- **NiFi**: Access the NiFi web interface at `https://localhost:8443/nifi`. The default login credentials are specified in the Dockerfile and docker-compose.yml.
- **MarkLogic**: Access the MarkLogic Admin Interface at `http://localhost:8001` for the first MarkLogic instance. Default login credentials are outlined in the docker-compose.yml file.

## Managing Services

Familiarize yourself with basic `docker-compose` commands for service management:

- **Start services**: `docker-compose up -d`
- **Stop services**: `docker-compose down`
- **View logs**: `docker-compose logs`

## Troubleshooting

If you encounter issues, consult the Docker and service logs for error messages. Common problems may include port conflicts, insufficient permissions, or environment variable misconfigurations.

## Conclusion

You have successfully set up and configured Apache NiFi and MarkLogic using Docker Compose. This setup provides a solid foundation for data processing and integration tasks within the BNSF MarkLogic Project. For further customization and advanced configurations, consult the official Docker, NiFi, and MarkLogic documentation.

[Back to Main README.md file](../../README.md)
