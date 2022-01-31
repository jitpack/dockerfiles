FROM ubuntu:16.04

MAINTAINER jitpack <jitpack@jitpack.io>

RUN dpkg --add-architecture i386 && \
    apt-get -qqy update && \ 
	apt-get -qqy install -y --no-install-recommends file git curl wget zip unzip xz-utils bzip2 nano less ca-certificates  && \
	apt-get -qqy install -y build-essential libncurses5:i386 libc6:i386 libstdc++6:i386 lib32gcc1 lib32z1 zlib1g:i386 && \
	apt-get -qqy install -y --no-install-recommends openjdk-8-jdk openjfx && \
	apt-get clean && \
	ln -sf /usr/lib/jvm/java-8-openjdk-amd64/bin/java /etc/alternatives/java

ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64

RUN adduser --disabled-password --gecos '' jitpack

WORKDIR /usr/lib/jvm
RUN wget -nv https://download.java.net/java/GA/jdk10/10/binaries/openjdk-10_linux-x64_bin.tar.gz && \
    tar xfz openjdk-10_linux-x64_bin.tar.gz && rm openjdk-10_linux-x64_bin.tar.gz

RUN wget -nv https://download.java.net/java/GA/jdk11/9/GPL/openjdk-11.0.2_linux-x64_bin.tar.gz && \
    tar xfz openjdk-11.0.2_linux-x64_bin.tar.gz && rm openjdk-11.0.2_linux-x64_bin.tar.gz && mv jdk-11.0.2 jdk-11

RUN wget -nv https://download.java.net/java/GA/jdk12.0.1/69cfe15208a647278a19ef0990eea691/12/GPL/openjdk-12.0.1_linux-x64_bin.tar.gz && \
    tar xfz openjdk-12.0.1_linux-x64_bin.tar.gz && rm openjdk-12.0.1_linux-x64_bin.tar.gz && mv jdk-12.0.1 jdk-12

RUN wget -nv https://download.java.net/java/GA/jdk13/5b8a42f3905b406298b72d750b6919f6/33/GPL/openjdk-13_linux-x64_bin.tar.gz && \
    tar xfz openjdk-13_linux-x64_bin.tar.gz && rm openjdk-13_linux-x64_bin.tar.gz

# Java 10
RUN cp -v /usr/lib/jvm/java-8-openjdk-amd64/jre/lib/security/cacerts /usr/lib/jvm/jdk-10/lib/security

