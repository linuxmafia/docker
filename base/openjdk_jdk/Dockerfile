FROM superwang/base.ubuntu
MAINTAINER Super Wayne <super.x.wayne@gmail.com>

RUN apt-get update && apt-get install openjdk-7-jdk -y --no-install-recommends && apt-get clean
RUN echo 'export JAVA_HOME=/usr/lib/jvm/java-7-openjdk-amd64' > /etc/profile.d/java.sh
RUN echo 'export PATH=${PATH}:${JAVA_HOME}/bin' >> /etc/profile.d/java.sh

RUN java -version
RUN javac -version

