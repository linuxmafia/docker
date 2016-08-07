FROM isuper/base-ubuntu
MAINTAINER Super Wayne <super.x.wayne@gmail.com>

ENV DEBIAN_FRONTEND noninteractive

ENV VERSION 8
ENV UPDATE 102
ENV BUILD 14

ENV JAVA_HOME /usr/lib/jvm/java-${VERSION}-oracle

ENV OPENSSL_VERSION 1.0.2h

RUN apt-get update && apt-get install ca-certificates curl \
	gcc libc6-dev libssl-dev make \
	-y --no-install-recommends && \
	curl --silent --location --retry 3 --cacert /etc/ssl/certs/GeoTrust_Global_CA.pem \
	--header "Cookie: oraclelicense=accept-securebackup-cookie;" \
	http://download.oracle.com/otn-pub/java/jdk/"${VERSION}"u"${UPDATE}"-b"${BUILD}"/jdk-"${VERSION}"u"${UPDATE}"-linux-x64.tar.gz \
	| tar xz -C /tmp && \
	mkdir -p /usr/lib/jvm && mv /tmp/jdk1.${VERSION}.0_${UPDATE} "${JAVA_HOME}" && \
	curl --silent --location --retry 3 --cacert /etc/ssl/certs/GlobalSign_Root_CA.pem \
	https://www.openssl.org/source/openssl-"${OPENSSL_VERSION}".tar.gz \
	| tar xz -C /tmp && \
	cd /tmp/openssl-"${OPENSSL_VERSION}" && \
		./config --prefix=/usr && \
		make clean && make && make install && \
	apt-get remove --purge --auto-remove -y \
		gcc \
		libc6-dev \
		libssl-dev \
		make && \
	apt-get autoclean && apt-get --purge -y autoremove && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN update-alternatives --install "/usr/bin/java" "java" "${JAVA_HOME}/bin/java" 1 && \
	update-alternatives --install "/usr/bin/javaws" "javaws" "${JAVA_HOME}/bin/javaws" 1 && \
	update-alternatives --install "/usr/bin/javac" "javac" "${JAVA_HOME}/bin/javac" 1 && \
	update-alternatives --set java "${JAVA_HOME}/bin/java" && \
	update-alternatives --set javaws "${JAVA_HOME}/bin/javaws" && \
	update-alternatives --set javac "${JAVA_HOME}/bin/javac"
