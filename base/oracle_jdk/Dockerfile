FROM superwang/base.ubuntu
MAINTAINER Super Wayne <super.x.wayne@gmail.com>

RUN apt-get install software-properties-common -y && add-apt-repository ppa:webupd8team/java -y && apt-get update

ENV VERSION 8

RUN echo oracle-java"${VERSION}"-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections
RUN apt-get install oracle-java"${VERSION}"-installer oracle-java"${VERSION}"-set-default -y

RUN apt-get clean && rm -rf /var/lib/apt/lists/*
RUN rm -rf /var/cache/oracle-jdk"${VERSION}"-installer

ENV JAVA_HOME /usr/lib/jvm/java-"${VERSION}"-oracle

RUN echo "${JAVA_HOME}"
RUN java -version
RUN javac -version

ENTRYPOINT /bin/bash
