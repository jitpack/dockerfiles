FROM jitpack/dockerfiles:base

MAINTAINER jitpack <jitpack@jitpack.io>

WORKDIR /opt

# tools
RUN apt-get install -y unzip
RUN apt-get install -y curl

# get maven 
RUN curl -sL http://mirrors.ukfast.co.uk/sites/ftp.apache.org/maven/maven-3/3.3.3/binaries/apache-maven-3.3.3-bin.tar.gz | gunzip | tar -x -C /opt
RUN ln -s /opt/apache-maven-3.3.3/bin/mvn /usr/local/bin

# get sbt
RUN curl -sL "http://dl.bintray.com/sbt/native-packages/sbt/0.13.8/sbt-0.13.8.tgz" | gunzip | tar -x -C /opt
RUN ln -s /opt/sbt/bin/sbt /usr/local/bin

# get gradle
ENV GRADLE_VERSION 2.9
RUN wget https://downloads.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip
RUN unzip "gradle-${GRADLE_VERSION}-bin.zip"
RUN ln -s "/opt/gradle-${GRADLE_VERSION}/bin/gradle" /usr/local/bin
RUN rm "gradle-${GRADLE_VERSION}-bin.zip"

RUN adduser --disabled-password --gecos '' jitpack
