FROM isuper/java-oracle
MAINTAINER Super Wayne <super.x.wayne@gmail.com>

RUN apt-get update && apt-get install ca-certificates curl -y 
RUN apt-get clean && apt-get --purge autoremove && rm -rf /var/lib/apt/lists/*

ENV VERSION 1.7.1

RUN curl --silent --location --retry 3 --cacert /etc/ssl/certs/thawte_Primary_Root_CA.pem \
	https://archive.apache.org/dist/tomee/tomee-"${VERSION}"/apache-tomee-"${VERSION}"-plus.tar.gz \
	| tar xz -C /tmp

ENV CATALINA_HOME /opt/apache-tomee-${VERSION}
ENV PATH ${CATALINA_HOME}/bin:$PATH

RUN mv /tmp/apache-tomee-plus-${VERSION} ${CATALINA_HOME}
RUN rm -rf ${CATALINA_HOME}/bin/*.bat && rm -rf ${CATALINA_HOME}/webapps/*
WORKDIR ${CATALINA_HOME}

RUN rm -rf /tmp/*

EXPOSE 8005
EXPOSE 8080
EXPOSE 8443
EXPOSE 8009

CMD $CATALINA_HOME/bin/catalina.sh run
