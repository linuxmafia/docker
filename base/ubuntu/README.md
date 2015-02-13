## Base and latest Ubuntu OS image

This repository contains **Dockerfile** of [Ubuntu](http://www.ubuntu.com/) for [Docker](https://www.docker.com/)'s [automated build](https://registry.hub.docker.com/u/isuper/base.ubuntu/) published to the public [Docker Hub Registry](https://registry.hub.docker.com/).

### Docker Tags

`isuper/base.ubuntu` provides only one single tagged image:

* `latest` (default): based on `ubuntu:latest`

### Installation

1. Install [Docker](https://www.docker.com/).

2. Download [automated build](https://registry.hub.docker.com/u/isuper/base.ubuntu/) from public [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull isuper/base.ubuntu`

    (alternatively, you can build an image from Dockerfile: `docker build -t="isuper/base.ubuntu" github.com/orgisuper/docker/tree/master/base/ubuntu`)

### Usage

    docker run -it --rm isuper/base.ubuntu
