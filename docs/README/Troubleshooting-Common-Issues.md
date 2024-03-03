[Back to Main README.md file](../../README.md)

# Troubleshooting Common Issues

This document provides solutions and troubleshooting steps for common issues encountered during the setup and operation of the BNSF MarkLogic Project, focusing on Docker, Apache NiFi, and MarkLogic services.

## Docker Troubleshooting

### Issue: Docker Containers Fail to Start
- **Solution**: Ensure Docker daemon is running. Check for error messages using `docker-compose up` (without `-d`) to see real-time container logs.

### Issue: Port Conflicts
- **Solution**: Verify that no other services are running on the ports designated in your `docker-compose.yml`. Use `netstat -tuln` (Linux/Mac) or `Get-Process -Id (Get-NetTCPConnection -LocalPort yourPort).OwningProcess` (Windows PowerShell) to check for port usage.

### Issue: Insufficient Permissions
- **Solution**: Ensure the current user has permissions to access Docker and manage containers. Adding the user to the Docker group (Linux) or running Docker Desktop with administrative privileges (Windows) can resolve this.

## Apache NiFi Troubleshooting

### Issue: NiFi Web Interface Unreachable
- **Solution**: Check if NiFi container is running using `docker ps`. Inspect NiFi logs within the container for errors (`docker logs <nifi-container-id>`). Ensure port forwarding is correctly set up in `docker-compose.yml`.

### Issue: Processors Failing to Start
- **Solution**: Review processor configurations for missing or incorrect parameters. Check for detailed error messages in the NiFi log files.

### Issue: SSL/TLS Configuration Errors
- **Solution**: Verify that keystore and truststore configurations are correct and that all referenced files are accessible to the NiFi container. Ensure passwords in the NiFi configuration match those used to secure the keystores.

## MarkLogic Troubleshooting

### Issue: MarkLogic Service Not Starting
- **Solution**: Confirm that the MarkLogic container is running (`docker ps`). Review the container's logs for errors (`docker logs <marklogic-container-id>`). Common issues include license agreement acceptance and initial setup not completed.

### Issue: Database Connection Issues
- **Solution**: Check network configurations and port mappings in `docker-compose.yml`. Ensure client applications are configured to use the correct ports and IP addresses.

### Issue: Data Restoration Problems
- **Solution**: Verify the integrity and compatibility of the backup data. Ensure that the MarkLogic container has sufficient permissions to access and modify the data directories mounted as volumes.

## General Tips

- **Clearing Docker Cache**: Sometimes, Docker might use cached layers that contain errors. Use `docker-compose build --no-cache` to rebuild images from scratch.
- **Resource Constraints**: Ensure your Docker environment is allocated enough CPU, memory, and disk resources, especially when running multiple services like NiFi and MarkLogic.
- **Networking Issues**: For networking-related problems, inspect Docker networks (`docker network ls`) and ensure containers are connected to the correct network.

## Conclusion

Troubleshooting involves systematically diagnosing and resolving issues that arise. This guide covers common scenarios, but unique problems may require further investigation. Consult official documentation and community forums for additional insights and support.

[Back to Main README.md file](../../README.md)