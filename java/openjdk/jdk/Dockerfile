FROM isuper/base-ubuntu
MAINTAINER Super Wayne <super.x.wayne@gmail.com>

ENV VERSION 7

RUN apt-get update && apt-get install software-properties-common -y && \
	add-apt-repository ppa:openjdk-r/ppa -y && apt-get update && \
	apt-get install openjdk-"${VERSION}"-jdk -y --no-install-recommends && \
	apt-get autoclean && apt-get --purge -y autoremove && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ENV JAVA_HOME /usr/lib/jvm/java-${VERSION}-openjdk-amd64
