# BNSF MarkLogic Project

## Overview

The BNSF MarkLogic Project is designed for the BNSF Railway Company, integrating advanced data processing capabilities using Apache NiFi. This solution emphasizes seamless connectivity with Microsoft SQL Server and MarkLogic databases, facilitated by Docker and Docker Compose for efficient deployment and streamlined management.

## Project Structure

- **`docker-compose.yml`**: Orchestrates a Docker environment with Apache NiFi and MarkLogic database instances for robust data handling.
- **`nifi/`**: Central directory for NiFi configurations.
  - **`Dockerfile`**: Specifies the custom Apache NiFi image, including security configurations and essential extensions.
  - **`extensions/`**: Houses additional NiFi extensions to extend functionality.
    - `mssql-jdbc-10.2.0.jre11.jar`: Enables Microsoft SQL Server connectivity.
    - `nifi-marklogic-nar-1.16.3.2.nar`: Integrates NiFi with MarkLogic databases.
    - `nifi-marklogic-services-api-nar-1.16.3.2.nar`: Provides API services for MarkLogic interactions.

## Prerequisites

Before you begin, ensure you have Docker and Docker Compose installed on your system.

## Setup and Deployment

1. **Clone the Repository**: Obtain a local copy of the project repository.
2. **Project Directory**: Navigate to the root directory of the project.
3. **Initialize Services**:
   ```bash
   docker-compose up -d
   ```
   This command builds and starts the services in detached mode.
4. **Access NiFi**: The NiFi web interface is available at `https://localhost:8443/nifi`.

## Configuration

Adjust the `docker-compose.yml` file to tailor environment variables such as credentials, hostnames, and data directories to your specific needs for NiFi and MarkLogic.

## Security Considerations

For production environments, it's critical to replace default passwords and enhance security configurations within the `docker-compose.yml` and NiFi `Dockerfile`.

## Importing BNSF Bookmarks into Chrome

To streamline access to project resources, the `BNSF_bookmarks.html` includes essential bookmarks:

1. Open Chrome and navigate to the Bookmark Manager via the menu (`Bookmarks` > `Bookmark manager`).
2. Use the manager's import function to select and open the `BNSF_bookmarks.html` from your project directory.
3. Imported bookmarks will appear in a new "Bookmarks bar" folder, providing quick access to project-related links.

