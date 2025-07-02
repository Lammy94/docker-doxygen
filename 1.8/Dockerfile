FROM alpine:3.20

LABEL maintainer="nakat-t <armaiti.wizard@gmail.com>" \
      description="Docker image for Doxygen documentation generator."

# Set environment variables for versions
ENV DOXYGEN_VERSION=1.11.0-r0
ENV GRAPHVIZ_VERSION=9.0.0-r2

# Install Doxygen and Graphviz
RUN apk update && \
    apk add --no-cache \
    doxygen=${DOXYGEN_VERSION} \
    graphviz=${GRAPHVIZ_VERSION} \
    fontconfig \
    font-noto \
    font-noto-emoji \
    font-noto-cjk

# Verify installation (optional, but good for debugging)
RUN doxygen --version
RUN dot -V

# Set the working directory
WORKDIR /data

ENTRYPOINT ["doxygen"]