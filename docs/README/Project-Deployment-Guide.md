[Back to Main README.md file](../../README.md)

# Deployment Instructions for the Project

This guide provides detailed instructions on how to deploy the project to both local and production environments. The deployment process involves setting executable permissions for the Gradle wrapper and using Gradle to deploy the project, with configurations specified in `gradle-local.properties` for local deployment and `gradle-prod.properties` for production deployment.

## Prerequisites

- A Unix-like environment (Linux, macOS, or WSL on Windows) for local deployment; appropriate access for production deployment
- Gradle installed or accessible via the Gradle wrapper (`gradlew`)
- Access to the project's repository and necessary permissions to execute scripts

## Local Deployment Steps

1. **Open Terminal**:
   Navigate to the root directory of your project in a terminal window.

2. **Set `gradlew` Execute Privileges**:
   Ensure the Gradle wrapper has execute permissions with the command:
   ```bash
   chmod +x gradlew
   ```

3. **Configure `gradle-local.properties`**:
   Ensure that you have a file named `gradle-local.properties` in your project directory. This file should contain necessary local environment variables such as `mlUsername` and `mlPassword`. These variables are used during the deployment process. Your `gradle-local.properties` might look something like this:
   ```
   mlUsername=admin
   mlPassword=admin
   ```
   Make sure not to commit sensitive data like passwords to your version control system.

4. **Deploy**:
   Use the Gradle wrapper to deploy locally:
   ```bash
   ./gradlew mlDeploy
   ```

5. **Verify Deployment**:
   Check that the deployment to your local environment is successful.

## Production Deployment Steps

1. **Prepare `gradle-prod.properties`**:
   Create or update a `gradle-prod.properties` file with production-specific configurations. Example:
   ```
   mlHost=
   mlUsername=rgarcia
   # Use secure methods to handle the mlPassword
   mlPassword=[SECURE_PASSWORD]
   # Specify if using a load balancer
   mlIsHostLoadBalancer=false
   ```
   **Important:** Securely manage sensitive information, especially passwords.

2. **Deploy to Production**:
   Deploy your project to the production environment using:

   ```bash
   ./gradlew mlDeploy -PenvironmentName=prod
   ```

   This command uses configurations from `gradle-prod.properties`.

3. **Post-Deployment**:
   - Verify that the project has been successfully deployed to production.
   - Conduct any necessary post-deployment checks or monitoring.

## Troubleshooting

- Ensure prerequisites are met for both environments.
- Confirm the correct setup of `gradle-local.properties` and `gradle-prod.properties`.
- Review terminal outputs for error diagnostics.

## Conclusion

This guide facilitates deployment to both local and production environments, emphasizing secure handling of sensitive configurations. Adjust the steps as necessary for your project specifics and infrastructure requirements.