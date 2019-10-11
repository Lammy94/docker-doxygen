FROM openjdk:8-jre-alpine
LABEL maintainer="nakat-t <armaiti.wizard@gmail.com>" \
      description="Docker image for Doxygen documentation generator."

ENV DOXYGEN_VERSION=1.8.16-r0
ENV GRAPHVIZ_VERSION=2.40.1-r1
ENV PLANTUML_VERSION=1.2019.11

RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/main/ >> /etc/apk/repositories

RUN apk add --no-cache doxygen=${DOXYGEN_VERSION} graphviz=${GRAPHVIZ_VERSION} fontconfig ttf-dejavu curl \
	&& mkdir -p /opt/plantuml \
	&& curl -L https://sourceforge.net/projects/plantuml/files/plantuml.${PLANTUML_VERSION}.jar/download -o /opt/plantuml/plantuml.jar \
	&& apk del curl

WORKDIR /work
