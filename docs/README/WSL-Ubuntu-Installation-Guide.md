[Back to Main README.md file](../../README.md)

# Installing Ubuntu 22.04 with Windows Subsystem for Linux (WSL) Version 2 on Windows 10

This README provides instructions for installing Ubuntu 22.04 using Windows Subsystem for Linux (WSL) version 2 on a Windows 10 system.

## Prerequisites

- Windows 10 (Updated to the latest version)
- An internet connection

## Step-by-Step Installation Guide

### 1. Enable the Windows Subsystem for Linux

First, enable the "Windows Subsystem for Linux" optional feature.

1. Open PowerShell as Administrator and run:
   ```bash
   dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
   ```

### 2. Enable the 'Virtual Machine Platform' Optional Feature

WSL 2 requires the 'Virtual Machine Platform' feature.

1. Open PowerShell as Administrator and run:
   ```bash
   dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
   ```

2. Restart your computer to complete the WSL install and update to WSL 2.

### 3. Download the Linux Kernel Update Package

Download and install the WSL 2 Linux kernel update package for x64 machines from the [official Microsoft link](https://aka.ms/wsl2kernel).

### 4. Set WSL 2 as Your Default Version

1. Open PowerShell as Administrator and run:
   ```bash
   wsl --set-default-version 2
   ```

### 5. Install Ubuntu 22.04

1. Open the Microsoft Store and search for "Ubuntu 22.04".

2. Select "Ubuntu 22.04 LTS" from the search results and click on 'Get' to download and install it.

### 6. Initialize Ubuntu 22.04

1. Launch Ubuntu 22.04 from the Start menu.

2. Follow the on-screen instructions to set up your new Ubuntu distribution, including creating a user account and password.

## Post-Installation Steps

After installation, you can update and upgrade Ubuntu 22.04 packages by running:

```bash
sudo apt update -y && sudo apt upgrade -y && sudo apt install default-jdk -y && sudo apt-get upgrade ca-certificates-java -y
```

## Troubleshooting

If you encounter issues during installation, refer to the [WSL installation guide](https://docs.microsoft.com/en-us/windows/wsl/install-win10) for additional troubleshooting steps.

## Conclusion

You now have Ubuntu 22.04 installed and running on your Windows 10 machine using WSL version 2. Enjoy the integration of Linux and Windows environments!

---

This README is specifically tailored for installing Ubuntu 22.04 with WSL 2. It's important to keep documentation like this updated, especially if new updates or changes occur in the installation process.

[Back to Main README.md file](../../README.md)