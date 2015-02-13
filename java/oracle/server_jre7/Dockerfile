FROM isuper/base-ubuntu
MAINTAINER Super Wayne <super.x.wayne@gmail.com>

RUN apt-get update && apt-get install ca-certificates curl -y 
RUN apt-get clean && apt-get --purge autoremove && rm -rf /var/lib/apt/lists/*

ENV VERSION 7
ENV UPDATE 76
ENV BUILD 13

RUN curl --silent --location --retry 3 --cacert /etc/ssl/certs/GeoTrust_Global_CA.pem \
	--header "Cookie: oraclelicense=accept-securebackup-cookie;" \
	http://download.oracle.com/otn-pub/java/jdk/"${VERSION}"u"${UPDATE}"-b"${BUILD}"/server-jre-"${VERSION}"u"${UPDATE}"-linux-x64.tar.gz \
	 | tar xz -C /tmp

ENV JAVA_HOME /usr/lib/jvm/java-${VERSION}-oracle
ENV JRE_HOME ${JAVA_HOME}/jre

RUN mkdir -p /usr/lib/jvm && mv /tmp/jdk1.${VERSION}.0_${UPDATE} "${JAVA_HOME}"
RUN update-alternatives --install "/usr/bin/java" "java" "${JRE_HOME}/bin/java" 1
RUN update-alternatives --install "/usr/bin/javac" "javac" "${JAVA_HOME}/bin/javac" 1
RUN update-alternatives --set java "${JRE_HOME}/bin/java"
RUN update-alternatives --set javac "${JAVA_HOME}/bin/javac"

RUN rm -rf /tmp/* && rm -rf /var/tmp/*

ENTRYPOINT /bin/bash

CMD java -version && javac -version

