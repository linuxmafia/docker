FROM isuper/java-oracle
MAINTAINER Super Wayne <super.x.wayne@gmail.com>

ENV VERSION 1.7.1

ENV CATALINA_HOME /opt/apache-tomee-${VERSION}
ENV PATH ${CATALINA_HOME}/bin:$PATH

RUN curl --silent --location --retry 3 http://archive.apache.org/dist/tomee/tomee-"${VERSION}"/apache-tomee-"${VERSION}"-plus.tar.gz | tar xz -C /tmp && \
	mv /tmp/apache-tomee-plus-${VERSION} ${CATALINA_HOME}
	rm -rf ${CATALINA_HOME}/bin/*.bat && rm -rf ${CATALINA_HOME}/webapps/* && \
	apt-get update && apt-get install -y --no-install-recommends gcc libc6-dev libssl-dev make && \
	curl --silent --location --retry 3 http://www.apache.org/dist/apr/apr-1.5.1.tar.gz | tar xz -C /tmp && \
	cd /tmp/apr-1.5.1 && ./configure && make clean && make && make install && \
	curl --silent --location --retry 3 http://www.apache.org/dist/tomcat/tomcat-connectors/native/1.1.33/source/tomcat-native-1.1.33-src.tar.gz | tar xz -C /tmp && \
	cd /tmp/tomcat-native-1.1.33-src/jni/native && ./configure -with-apr=/usr/local/apr/ -with-ssl=/usr -with-java-home=${JAVA_HOME} -prefix=/usr/lib/java -libdir=/usr/lib/java && make clean && make && make install && \
	apt-get remove --purge --auto-remove -y gcc libc6-dev libssl-dev make && \
	apt-get autoclean && apt-get --purge -y autoremove && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ENV LD_LIBRARY_PATH='$LD_LIBRARY_PATH:/usr/lib/java'

COPY files/conf/ ${CATALINA_HOME}/conf/

WORKDIR ${CATALINA_HOME}

EXPOSE 8005
EXPOSE 8080
EXPOSE 8443
EXPOSE 8009


CMD ${CATALINA_HOME}/bin/catalina.sh run
