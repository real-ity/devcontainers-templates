FROM storm:${templateOption:stormVersion} AS storm 

FROM mcr.microsoft.com/devcontainers/java:1-${templateOption:javaVersion}-${templateOption:imageVariant}
ARG DISTRO_NAME=apache-storm-${templateOption:stormVersion}
ENV PATH $PATH:/$DISTRO_NAME/bin \
    JAVA_HOME=/docker-java-home \
    STORM_CONF_DIR=/conf \
    STORM_DATA_DIR=/data \
    STORM_LOG_DIR=/logs

RUN mkdir -p "$STORM_CONF_DIR" "$STORM_DATA_DIR" "$STORM_LOG_DIR"; \
    chown -R vscode:vscode "$STORM_CONF_DIR" "$STORM_DATA_DIR" "$STORM_LOG_DIR";

COPY --from=storm --chown=vscode:vscode /$DISTRO_NAME /$DISTRO_NAME
