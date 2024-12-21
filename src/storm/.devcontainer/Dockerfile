FROM storm:${templateOption:stormVersion} AS storm 

ARG DISTRO_NAME=apache-storm-${templateOption:stormVersion}
FROM mcr.microsoft.com/devcontainers/java:1-${templateOption:javaVersion}-${templateOption:imageVariant}
COPY --from=storm /apache-storm-* /
ENV PATH $PATH:/$DISTRO_NAME/bin
