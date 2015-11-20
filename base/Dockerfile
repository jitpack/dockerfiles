FROM ubuntu:14.04

MAINTAINER jitpack <jitpack@jitpack.io>

# jdks

RUN echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | sudo /usr/bin/debconf-set-selections

RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | sudo /usr/bin/debconf-set-selections

RUN apt-get install -y software-properties-common && add-apt-repository -y ppa:webupd8team/java && \ 
    apt-get update && \ 
	apt-get install -y git curl unzip \
	oracle-java7-installer \
	oracle-java8-installer

RUN adduser --disabled-password --gecos '' jitpack
