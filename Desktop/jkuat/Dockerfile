#start with a base image
FROM ubuntu:14.04
#install java
RUN apt-get update && apt-get -y upgrade && apt-get -y install software-properties-common && \
apt-get -y install default-jre && apt-get -y install default-jdk && \
apt-get -y install curl && add-apt-repository ppa:openjdk-r/ppa && \
apt-get update && apt-get -y install openjdk-8-jre && apt-get -y install openjdk-8-jdk
#set up git & sbt
RUN curl -L -o sbt-0.13.15.deb https://dl.bintray.com/sbt/debian/sbt-0.13.15.deb && \
  dpkg -i sbt-0.13.15.deb && \
  rm sbt-0.13.15.deb && \
  apt-get update && apt-get -y install git  
#install framework
RUN mkdir ussd/
WORKDIR ussd/
COPY . ussd/
RUN cd ussd/ && sbt 
CMD ["sbt","run"]

