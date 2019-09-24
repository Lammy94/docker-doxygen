# Supported tags

* `latest`, `1.8`, `1.8.16`
* `plantuml`, `1.8-plantuml`, `1.8.16-plantuml`, `1.8.16-plantuml-1.2019.11`

# Introduction

Dockerfile to build a doxygen container image.

# How to use this image

## Quick Start

Mount the directory containing the Doxyfile and source files on `/work` and run the container.

```
docker run -it --rm -v $PWD:/work nakatt/doxygen doxygen
```

## Use PlantUML

PlantUML is installed in `/opt/plantuml/plantuml.jar`. When using PlantUML, add a following line in Doxyfile.

```
PLANTUML_JAR_PATH = /opt/plantuml/plantuml.jar
```

# Image Variants

## `doxygen:<version>`

This is the defacto image containing only doxygen and graphviz. This image is based on alpine.

## `doxygen:<version>-plantuml-<version>`

This image has plantuml installed in addition to doxygen and graphviz. Since plantuml requires java, this image is based on openjdk, not alpine.

