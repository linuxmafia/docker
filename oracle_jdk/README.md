## Java provided by Oracle

This repository contains **Dockerfile** of [Java SE](http://java.oracle.com/) for [Docker](https://www.docker.com/)'s [automated build](https://registry.hub.docker.com/u/isuper/java-oracle/) published to the public [Docker Hub Registry](https://registry.hub.docker.com/).

To use this image, you must accept the [Oracle Binary Code License Agreement](http://www.oracle.com/technetwork/java/javase/terms/license/index.html) for Java SE.

### Docker Tags

`isuper/java-oracle` provides several tagged images:

* `latest` (default): pointed to `isuper/java-oracle:server_jre_latest`

* `server_jre_latest`: pointed to `isuper/java-oracle:server_jre_8`
* `server_jre_8`: based on `Oracle Java SE Server Runtime Environment 8 update 77 build 03`
* `server_jre_7`: based on `Oracle Java SE Server Runtime Environment 7 update 80 build 15`

* `jre_latest`: pointed to `isuper/java-oracle:jre_8`
* `jre_8`: based on `Oracle Java SE Runtime Environment 8 update 77 build 03`
* `jre_7`: based on `Oracle Java SE Runtime Environment 7 update 80 build 15`

* `jdk_latest`: pointed to `isuper/java-oracle:jdk_8`
* `jdk_8`: based on `Oracle Java SE Development Kit 8 update 77 build 03`
* `jdk_7`: based on `Oracle Java SE Development Kit 7 update 80 build 15`

### Installation

1. Install [Docker](https://www.docker.com/).

2. Download [automated build](https://registry.hub.docker.com/u/isuper/java-oracle/) from public [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull isuper/java-oracle`

### Usage

    docker run -it isuper/java-oracle /bin/bash
