# Use apache/nifi base image
FROM apache/nifi:1.25.0 AS local-nifidev

# Set ARGs and ENVs
ARG KEYSTORE_PASSWORD=changeit
ARG NIFI_HOSTNAME=bnsfNifi
ARG NIFI_USERNAME=admin
ARG NIFI_PASSWORD=adminpassword

ENV NIFI_BASE_DIR=/opt/nifi \
    NIFI_HOME=${NIFI_BASE_DIR}/nifi-current \
    NIFI_TOOLKIT_HOME=${NIFI_BASE_DIR}/nifi-toolkit-current \
    AUTH=tls \
    KEYSTORE_PATH=${NIFI_BASE_DIR}/certs/keystore.jks \
    KEYSTORE_TYPE=jks \
    KEYSTORE_PASSWORD=${KEYSTORE_PASSWORD} \
    TRUSTSTORE_PATH=${NIFI_BASE_DIR}/certs/truststore.jks \
    TRUSTSTORE_PASSWORD=${KEYSTORE_PASSWORD} \
    TRUSTSTORE_TYPE=jks \
    NIFI_WEB_HTTPS_HOST=${NIFI_HOSTNAME} \
    NIFI_SECURITY_USER_AUTHORIZER=single-user-authorizer \
    NIFI_SECURITY_USER_LOGIN_IDENTITY_PROVIDER=single-user-provider \
    NIFI_JVM_HEAP_MIN=4g \
    NIFI_JVM_HEAP_MAX=8g
    
# Copy the MarkLogic NiFi JARs
COPY extensions/*.nar ${NIFI_HOME}/extensions

# Switch to root to install Vim
USER root

# Install Vim, net-tools, and inetutils
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install -y vim net-tools iputils-ping



# Switch to user nifi for security
USER nifi

# Create necessary directories
RUN mkdir -p ${NIFI_BASE_DIR}/certs
RUN mkdir -p ${NIFI_BASE_DIR}/gencerts
RUN mkdir -p ${NIFI_BASE_DIR}/dataload
RUN mkdir -p ${NIFI_BASE_DIR}/staging-data

# Regenerate SSL/TLS keystores using nifi-toolkit and copy the certs to /opt/nifi/certs
RUN ${NIFI_TOOLKIT_HOME}/bin/tls-toolkit.sh standalone -d 99999 -n ${NIFI_HOSTNAME} \
    --subjectAlternativeNames localhost,${NIFI_HOSTNAME}.local \
    -o ${NIFI_BASE_DIR}/gencerts \
    -K ${KEYSTORE_PASSWORD} \
    -P ${KEYSTORE_PASSWORD} \
    -S ${KEYSTORE_PASSWORD} \
    -B ${KEYSTORE_PASSWORD} \
    -f ${NIFI_HOME}/conf/nifi.properties && \
    find ${NIFI_BASE_DIR}/gencerts -type f -exec cp -v {} ${NIFI_BASE_DIR}/certs \; && \
    rm -rf ${NIFI_BASE_DIR}/gencerts && \
    # Set initial username and password based on build arguments
    ${NIFI_HOME}/bin/nifi.sh set-single-user-credentials "${NIFI_USERNAME}" "${NIFI_PASSWORD}" && \
    # Set alias for user convenience
    echo "alias ll='ls -lart --color=auto'" >> /home/nifi/.bash_aliases

# Set the work directory
WORKDIR ${NIFI_HOME}