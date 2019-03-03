FROM ubuntu:16.04

MAINTAINER jitpack <jitpack@jitpack.io>

RUN dpkg --add-architecture i386 && \
    apt-get update && \ 
	apt-get install -y --no-install-recommends file git curl wget zip unzip xz-utils nano less && \
	apt-get install -y libncurses5:i386 libc6:i386 libstdc++6:i386 lib32gcc1 lib32z1 zlib1g:i386 && \
	apt-get install -y --no-install-recommends openjdk-8-jdk openjfx && \
	apt-get clean && \
	ln -sf /usr/lib/jvm/java-8-openjdk-amd64/bin/java /etc/alternatives/java

ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64

RUN adduser --disabled-password --gecos '' jitpack

WORKDIR /usr/lib/jvm
RUN wget https://download.java.net/java/GA/jdk10/10/binaries/openjdk-10_linux-x64_bin.tar.gz && \
    tar xfz openjdk-10_linux-x64_bin.tar.gz && rm openjdk-10_linux-x64_bin.tar.gz

RUN wget https://download.java.net/java/GA/jdk11/9/GPL/openjdk-11.0.2_linux-x64_bin.tar.gz && \
    tar xfz openjdk-11.0.2_linux-x64_bin.tar.gz && rm openjdk-11.0.2_linux-x64_bin.tar.gz

#USER jitpack
#WORKDIR /home/jitpack
