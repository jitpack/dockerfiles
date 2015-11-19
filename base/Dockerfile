FROM ubuntu:14.04

MAINTAINER jitpack <jitpack@jitpack.io>

RUN apt-get update
RUN apt-get install -y software-properties-common
RUN apt-get install -y git

# jdks

RUN add-apt-repository -y ppa:webupd8team/java
RUN apt-get update

RUN echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | sudo /usr/bin/debconf-set-selections
RUN apt-get install -y oracle-java7-installer

RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | sudo /usr/bin/debconf-set-selections
RUN apt-get install -y oracle-java8-installer

