# openjdk:8-jre-alpine no longer supported so install openjdk11-jdk ourselves instead
FROM alpine:3.20 

LABEL maintainer="nakat-t <armaiti.wizard@gmail.com>" \
      description="Docker image for Doxygen and PlantUML documentation generator."

# Set environment variables for versions
ENV DOXYGEN_VERSION=1.11.0-r0
ENV GRAPHVIZ_VERSION=9.0.0-r2

# PlantUML version and installation directory
ENV PLANTUML_VERSION=1.2025.4
ENV PLANTUML_INSTALL_DIR=/opt/plantuml

# Install OpenJDK 19 (JDK), Doxygen, Graphviz, Fontconfig, and PlantUML dependencies
RUN apk update && \
    apk add --no-cache openjdk11-jdk \
    doxygen=${DOXYGEN_VERSION} \
    graphviz=${GRAPHVIZ_VERSION} \
    fontconfig \
    font-noto \
    font-noto-emoji \
    font-noto-cjk \
    curl

# Install PlantUML
RUN mkdir -p ${PLANTUML_INSTALL_DIR} && \
    curl -L "https://github.com/plantuml/plantuml/releases/download/v${PLANTUML_VERSION}/plantuml-${PLANTUML_VERSION}.jar" -o ${PLANTUML_INSTALL_DIR}/plantuml.jar && \
    test -f ${PLANTUML_INSTALL_DIR}/plantuml.jar && \
    rm -rf /var/cache/apk/*

# Verify installations (optional, but good for debugging)
RUN java -version
RUN doxygen --version
RUN dot -V
RUN java -jar ${PLANTUML_INSTALL_DIR}/plantuml.jar -version

# Set the PLANTUML_JAR_PATH environment variable for Doxygen
ENV PLANTUML_JAR_PATH=${PLANTUML_INSTALL_DIR}/plantuml.jar

# Set the working directory
WORKDIR /data

ENTRYPOINT ["doxygen"]