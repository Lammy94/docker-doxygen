# Supported tags

* `latest`, `1.8`, `1.8.17`
* `plantuml`, `1.8-plantuml`, `1.8.17-plantuml`, `1.8.17-plantuml-1.2020.2`

# Introduction

Dockerfile to build a doxygen container image.

# How to use this image

## Quick Start

Mount the directory containing the Doxyfile and source files on `/data` and run the container.

```
# Generate config file
docker run -it --rm -v $PWD:/data nakatt/doxygen -g Doxyfile

# Edit config file
nano Doxyfile

# Run doxygen
docker run -it --rm -v $PWD:/data nakatt/doxygen
```

## Use variant images containing PlantUML

Images tagged with `plantuml` have PlantUML additionally installed. PlantUML is installed in `/opt/plantuml/plantuml.jar`.

When using PlantUML, add a following line in Doxyfile.

```
PLANTUML_JAR_PATH = $(PLANTUML_INSTALL_DIR)/plantuml.jar
```

# Image Variants

## `doxygen:<version>`

This is the defacto image containing only doxygen and graphviz. This image is based on alpine.

## `doxygen:<version>-plantuml-<version>`

This image has plantuml installed in addition to doxygen and graphviz. Since plantuml requires java, this image is based on openjdk, not alpine.

