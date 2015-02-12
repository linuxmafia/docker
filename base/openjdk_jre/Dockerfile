FROM superwang/base.ubuntu
MAINTAINER Super Wayne <super.x.wayne@gmail.com>

RUN apt-get install software-properties-common -y && add-apt-repository ppa:openjdk-r/ppa -y && apt-get update
RUN apt-get install openjdk-8-jre -y --no-install-recommends && apt-get clean
RUN echo 'export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64' > /etc/profile.d/java.sh
RUN echo 'export PATH=${PATH}:${JAVA_HOME}/bin' >> /etc/profile.d/java.sh

RUN java -version

