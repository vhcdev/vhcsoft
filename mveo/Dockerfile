FROM ubuntu:14.04
MAINTAINER Viet Hung Chu <viethungde@gmail.com>

#
# Oracle Java 8 Dockerfile
#
# https://github.com/dockerfile/java
# https://github.com/dockerfile/java/tree/master/oracle-java8
#
# Install Java.
# Add a repo where OpenJDK can be found.
RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:webupd8team/java
RUN apt-get update

# Auto-accept the Oracle JDK license
RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | sudo /usr/bin/debconf-set-selections

RUN apt-get install -y oracle-java8-installer
RUN apt-get install -y mp3gain
RUN apt-get install wget
VOLUME /tmp
RUN wget https://www.dropbox.com/s/m4l810a502wlrya/mveo-0.1.0.jar?dl=0 -O app.jar
#ADD sound.equalizer-0.1.0.jar app.jar
RUN bash -c 'touch /app.jar'
#RUN java -jar app.jar
EXPOSE 8080

COPY docker-entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]

