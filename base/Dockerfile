FROM ubuntu:16.04

MAINTAINER jitpack <jitpack@jitpack.io>

RUN dpkg --add-architecture i386 && \
    apt-get update && \ 
	apt-get install -y --no-install-recommends file git curl wget zip unzip && \
	apt-get install -y libncurses5:i386 libc6:i386 libstdc++6:i386 lib32gcc1 lib32z1 zlib1g:i386 && \
	apt-get install -y --no-install-recommends openjdk-8-jdk && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists /var/cache/apt && \
	ln -sf /usr/lib/jvm/java-8-openjdk-amd64/bin/java /etc/alternatives/java

ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64

RUN adduser --disabled-password --gecos '' jitpack
#USER jitpack
#WORKDIR /home/jitpack
