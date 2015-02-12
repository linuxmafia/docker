FROM superwang/base.ubuntu
MAINTAINER Super Wayne <super.x.wayne@gmail.com>

RUN apt-get install software-properties-common -y && add-apt-repository ppa:webupd8team/java -y && apt-get update
RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections
RUN apt-get install oracle-java8-installer oracle-java8-set-default -y && apt-get clean

RUN java -version
RUN javac -version
