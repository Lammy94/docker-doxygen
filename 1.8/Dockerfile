FROM alpine:3.10
LABEL maintainer="nakat-t <armaiti.wizard@gmail.com>" \
      description="Docker image for Doxygen documentation generator."

RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/main/ >> /etc/apk/repositories
RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing/ >> /etc/apk/repositories

ENV DOXYGEN_VERSION=1.8.16-r1
ENV GRAPHVIZ_VERSION=2.40.1-r1

RUN apk add --no-cache doxygen=${DOXYGEN_VERSION} graphviz=${GRAPHVIZ_VERSION} fontconfig ttf-dejavu font-ipa

WORKDIR /data
