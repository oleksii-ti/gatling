# Base Docker Image

* [java:8-jdk-alpine](https://registry.hub.docker.com/_/java/)


# Installation

* Install [Docker](https://www.docker.com/)

* Get automated build from public registry:

Latest version:

`docker pull oleksiit/gatling:latest`

All versions:

`docker pull oleksiit/gatling`

Specific version:

`docker pull oleksiit/gatling:3.5.1`

* [Alternatively] Build an image from Dockerfile: `docker build -t="oleksiit/gatling" github.com/oleksii-ti/gatling`

# Usage

Use image to run container

```
docker run -it --rm oleksiit/gatling
```

Mount configuration and simulation files from the host machine and run gatling in interactive mode

```
docker run -it --rm -v /home/core/gatling/conf:/opt/gatling/conf \
-v /home/core/gatling/user-files:/opt/gatling/user-files \
-v /home/core/gatling/results:/opt/gatling/results \
oleksiit/gatling
```

Use the `-e` switch to use JAVA_OPTS to pass parameters to gatling tests

```
docker run -e JAVA_OPTS="-Dusers=10" -it --rm oleksiit/gatling
```
