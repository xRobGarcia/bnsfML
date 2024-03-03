[Back to Main README.md file](../../README.md)

# Cloning and Configuring the `bnsfML` Repository

This guide outlines the steps to clone the `bnsfML` repository from GitHub using the GitHub CLI and set up your Git environment to ensure a seamless experience with this repository.

## Prerequisites

Ensure you have the following installed and set up before proceeding:

- **Git**: Necessary for version control and interacting with the GitHub repository.
- **Visual Studio Code (VS Code)**: Recommended as the default editor for code and commit messages.
- **GitHub Account**: Required for cloning and contributing to the repository.
- **GitHub CLI (gh)**: Facilitates command-line interaction with GitHub repositories.

## Installing GitHub CLI

Follow these steps to install the GitHub CLI if it's not already installed:

1. **Open a Terminal**: Launch your terminal application.

2. **Update Your Package List**: Ensure you have the latest versions of your packages.
   ```bash
   sudo apt update
   ```

3. **Install the GitHub CLI**:
   ```bash
   sudo apt install gh
   ```

## Cloning the Repository

To clone the `bnsfML` repository:

1. **Clone via GitHub CLI**:
   ```bash
   gh repo clone xRobGarcia/bnsfML
   ```
   This command clones the repository to your local machine.

2. **Change Directory**:
   ```bash
   cd bnsfML
   ```

## Configuring Git Settings

After cloning, apply the following Git configurations to optimize your setup:

1. **Set VS Code as the Default Editor**:
   Applies globally, making VS Code the default editor for Git operations.
   ```bash
   git config --global core.editor "code -n -w"
   ```

2. **Disable File Mode Tracking**:
   Useful in cross-operating system projects to ignore file permission changes.
   ```bash
   git config --global core.filemode false
   ```

3. **Manage Line Endings Across OSes**:
   Prevents Git from auto-converting line endings, maintaining consistency.
   ```bash
   git config --global core.autocrlf false
   ```

4. **Configure Credential Storage**:
   Uses the Git credential store globally for secure credential caching.
   ```bash
   git config --global credential.helper store
   ```

## Finalizing Your Setup

With these configurations, your Git environment is now fine-tuned for working on the `bnsfML` repository, ensuring smooth operation across different platforms and streamlining your development workflow.

[Back to Main README.md file](../../README.md)