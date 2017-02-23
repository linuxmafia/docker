## Tomcat EE image

This repository contains **Dockerfile** of [Ubuntu](http://www.ubuntu.com/) for [Docker](https://www.docker.com/)'s [automated build](https://registry.hub.docker.com/u/isuper/tomee-plus/) published to the public [Docker Hub Registry](https://registry.hub.docker.com/).

### Docker Tags

`isuper/tomee-plus` provides several tagged images:

* `latest` (default): pointed to `7.0.2`
* `7.0.2` : Tomcat EE version `7.0.2`
* `1.7.4` : Tomcat EE version `1.7.4`
* `1.7.3` : Tomcat EE version `1.7.3`

### Installation

1. Install [Docker](https://www.docker.com/).

2. Download [automated build](https://registry.hub.docker.com/u/isuper/tomee-plus/) from public [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull isuper/tomee-plus`

    (alternatively, you can build an image from Dockerfile: `docker build -t="isuper/tomee-plus" https://raw.githubusercontent.com/orgisuper/docker/TOMEE/tomee-plus/Dockerfile`)

### Usage

    docker run -d -p 8080:8080 -p 8443:8443 isuper/tomee-plus
