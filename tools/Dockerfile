FROM jitpack/base

MAINTAINER jitpack <jitpack@jitpack.io>

WORKDIR /opt

# get maven 
RUN wget https://archive.apache.org/dist/maven/maven-3/3.5.3/binaries/apache-maven-3.5.3-bin.zip && \
    unzip apache-maven-3.5.3-bin.zip && \
    ln -s /opt/apache-maven-3.5.3/bin/mvn /usr/local/bin && \
    rm apache-maven-3.5.3-bin.zip

# get sbt
RUN curl -sL "http://dl.bintray.com/sbt/native-packages/sbt/0.13.15/sbt-0.13.15.tgz" | gunzip | tar -x -C /opt && \
    ln -s /opt/sbt/bin/sbt /usr/local/bin

# get gradle
ENV GRADLE_VERSION 4.8.1
RUN wget https://downloads.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip && \
    unzip "gradle-${GRADLE_VERSION}-bin.zip" && \
    ln -s "/opt/gradle-${GRADLE_VERSION}/bin/gradle" /usr/local/bin && \
    rm "gradle-${GRADLE_VERSION}-bin.zip"

RUN curl -sL https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein -o /usr/local/bin/lein && \
    chmod 755 /usr/local/bin/lein && lein -v

