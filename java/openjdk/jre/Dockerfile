FROM isuper/base-ubuntu
MAINTAINER Super Wayne <super.x.wayne@gmail.com>

ENV VERSION 8

RUN apt-get update && apt-get install software-properties-common -y && add-apt-repository ppa:openjdk-r/ppa -y && apt-get update
RUN apt-get install openjdk-"${VERSION}"-jre -y --no-install-recommends
RUN apt-get clean && apt-get --purge autoremove && rm -rf /var/lib/apt/lists/*

ENV JAVA_HOME /usr/lib/jvm/java-${VERSION}-openjdk-amd64

RUN rm -rf /tmp/* && rm -rf /var/tmp/*

ENTRYPOINT /bin/bash

CMD java -version

