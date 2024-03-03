[Back to Main README.md file](../../README.md)

# Data Hub Central

This document provides instructions on how to download, install, and run Data Hub Central.

## Prerequisites

Ensure that you have Java installed on your system. Data Hub Central requires Java to run.

## Download

Use the following command to download Data Hub Central:

```
curl -k -L -O http://developer.marklogic.com/download/binaries/dhf/marklogic-data-hub-central-6.0.0.war
```

## Running Data Hub Central

Once the download is complete, you can run Data Hub Central using Java. Execute the following command:

```
java -jar marklogic-data-hub-central-6.0.0.war
```

This will start the application on your local machine.

## Running Data Hub Central in the Background

For seamless operation of Data Hub Central without the need to keep a terminal session active, you can run it in the background. This can be particularly useful for long-running processes or services that need to continue running after the terminal session has ended. Below are methods to achieve this on Unix-based systems, which can be adapted for use on other operating systems as well.

### Using `nohup`

The `nohup` command is a traditional way to run processes in the background on Unix-based systems, ensuring they continue to run even after the terminal is closed. Execute the following command in your terminal:

```bash
nohup java -jar marklogic-data-hub-central-6.0.0.war &
```

### Redirecting Output

Alternatively, you can start Data Hub Central in the background by redirecting its output to avoid cluttering your terminal with logs. This method also disassociates the process from the terminal session:

```bash
java -jar marklogic-data-hub-central-6.0.0.war > /dev/null 2>&1 &
```

This command redirects both standard output (`stdout`) and standard error (`stderr`) to `/dev/null`, effectively silencing all output from the process, and runs it in the background.

Both methods will initiate Data Hub Central in the background, allowing you to close the terminal or continue with other tasks without interrupting the running process.

## Log into Hub Central

In your web browser, navigate to [`http://localhost:8080/`](http://localhost:8080/) and log in using the following credentials:

```properties
username: hub-central-developer
password: password
```

Follow the on-screen instructions to start using Data Hub Central.

## Accessing Data Hub Central

After starting Data Hub Central, you can access it via your web browser. The default URL is usually `http://localhost:8080`.

## Stopping Data Hub Central

To stop Data Hub Central, you'll need to find the process ID (PID) and kill it. You can find the PID using commands like `ps` or `top` in Unix-based systems.

## Additional Information

For more detailed instructions and troubleshooting, refer to the official Data Hub Central documentation available on the MarkLogic website.

[Back to Main README.md file](../../README.md)