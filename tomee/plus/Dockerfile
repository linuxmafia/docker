FROM isuper/java-oracle
MAINTAINER Super Wayne <super.x.wayne@gmail.com>

ENV VERSION 1.7.1

RUN curl --silent --location --retry 3 http://archive.apache.org/dist/tomee/tomee-"${VERSION}"/apache-tomee-"${VERSION}"-plus.tar.gz | tar xz -C /tmp

ENV CATALINA_HOME /opt/apache-tomee-${VERSION}
ENV PATH ${CATALINA_HOME}/bin:$PATH

RUN mv /tmp/apache-tomee-plus-${VERSION} ${CATALINA_HOME}
RUN rm -rf ${CATALINA_HOME}/bin/*.bat && rm -rf ${CATALINA_HOME}/webapps/*

RUN apt-get update && apt-get install -y --no-install-recommends gcc libc6-dev libssl-dev make

RUN curl --silent --location --retry 3 http://www.apache.org/dist/apr/apr-1.5.1.tar.gz | tar xz -C /tmp
RUN cd /tmp/apr-1.5.1 && ./configure && make clean && make && make install
RUN curl --silent --location --retry 3 http://www.apache.org/dist/tomcat/tomcat-connectors/native/1.1.33/source/tomcat-native-1.1.33-src.tar.gz | tar xz -C /tmp
RUN cd /tmp/tomcat-native-1.1.33-src/jni/native && ./configure -with-apr=/usr/local/apr/ -with-ssl=/usr -with-java-home=${JAVA_HOME} -prefix=/usr/lib/java -libdir=/usr/lib/java && make clean && make && make install

ENV LD_LIBRARY_PATH='$LD_LIBRARY_PATH:/usr/lib/java'

COPY files/conf/ ${CATALINA_HOME}/conf/

WORKDIR ${CATALINA_HOME}

EXPOSE 8005
EXPOSE 8080
EXPOSE 8443
EXPOSE 8009

RUN apt-get remove --purge --auto-remove -y gcc libc6-dev libssl-dev make && apt-get clean && apt-get --purge -y autoremove && rm -rf /tmp/* /var/tmp/* /var/lib/apt/lists/*

CMD ${CATALINA_HOME}/bin/catalina.sh run
