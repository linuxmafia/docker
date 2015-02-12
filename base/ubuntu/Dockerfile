FROM ubuntu:latest
MAINTAINER Super Wayne <super.x.wayne@gmail.com>

RUN apt-get update && apt-get dist-upgrade -y
RUN apt-get clean && apt-get --purge autoremove && rm -rf /var/lib/apt/lists/*

RUN rm -rf /tmp/* && rm -rf /var/tmp/*

ENTRYPOINT /bin/bash
