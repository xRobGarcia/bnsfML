[Back to Main README.md file](../../README.md)

# Docker Installation and Integration with WSL on Windows 10

This README provides instructions for installing Docker on Windows 10 and integrating it with the Windows Subsystem for Linux (WSL).

## Prerequisites

- Windows 10 64-bit: Pro, Enterprise, or Education (Build 16299 or later).
- Hyper-V and Containers Windows features must be enabled.
- WSL with Ubuntu 22.04 (or similar) installed.

## Step-by-Step Installation Guide

### 1. Install Docker Desktop for Windows

1. **Download Docker Desktop for Windows**: Visit the [Docker Hub](https://hub.docker.com/editions/community/docker-ce-desktop-windows/) and download the Docker Desktop installer.

2. **Install Docker Desktop**: Run the installer and follow the on-screen instructions to complete the installation.

3. **Start Docker Desktop**: Docker Desktop does not start automatically after installation. To start Docker Desktop, search for Docker, and select `Docker Desktop` in the search results.

### 2. Configure Docker to Use WSL

1. **Open Docker Desktop Settings**: Right-click the Docker icon in the system tray and select 'Settings'.

2. **Enable WSL Integration**: In the settings menu, go to the 'Resources' section, and then to the 'WSL Integration' category.

3. **Choose Your WSL Distribution**: Enable integration with your installed distributions. If using Ubuntu 22.04, ensure it is selected.

4. **Apply & Restart**: Click 'Apply & Restart' to save your settings.


![Enable Ubuntu integration](<../images/Enable Ubuntu integration.png>)
### 3. Test Docker with WSL

1. **Open Your WSL Terminal**: Open your Ubuntu 22.04 (or similar) WSL terminal.

2. **Run a Test Docker Command**: For example, you can run the hello-world container:
   ```bash
   docker run hello-world
   ```

   This command downloads a test image and runs it in a container. If the installation was successful, you should see a message indicating that Docker is working correctly.

### 4. Using Docker in WSL

- **Manage Docker Containers**: You can use Docker commands in your WSL terminal just like you would on a native Linux system.
- **Developing with Docker**: You can develop your applications in WSL and use Docker to run your containers for testing and deployment.

## Troubleshooting

- If you encounter issues with Docker, ensure that your Windows 10 is up to date and that you have the correct version of WSL installed.
- Refer to the [Docker and WSL documentation](https://docs.docker.com/docker-for-windows/wsl/) for more detailed instructions and troubleshooting tips.

## Conclusion

You now have Docker installed and integrated with WSL on your Windows 10 machine. This setup allows you to develop in a Linux environment and use Docker containers seamlessly.

---

Remember to update this README if there are new versions of Docker or changes in the installation process. This guide is a starting point and can be expanded to include more specific use cases or advanced configurations.

[Back to Main README.md file](../../README.md)