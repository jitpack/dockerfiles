FROM jitpack/base

MAINTAINER jitpack <jitpack@jitpack.io>

WORKDIR /opt

# get maven 
RUN wget https://archive.apache.org/dist/maven/maven-3/3.6.1/binaries/apache-maven-3.6.1-bin.zip && \
    unzip apache-maven-3.6.1-bin.zip && \
    ln -s /opt/apache-maven-3.6.1/bin/mvn /usr/local/bin && \
    rm apache-maven-3.6.1-bin.zip

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

RUN curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | bash
RUN apt-get update && apt-get install -y python git-lfs

# get ant
RUN wget https://archive.apache.org/dist/ant/binaries/apache-ant-1.10.0-bin.zip && \
    unzip apache-ant-1.10.0-bin.zip && \
    ln -s /opt/apache-ant-1.10.0/bin/ant /usr/local/bin && \
    rm apache-ant-1.10.0-bin.zip

RUN su jitpack -c 'curl -s "https://get.sdkman.io" | bash'

#RUN apt-get update && apt-get install docker.io cgroup-lite screen -y && apt-get clean && \
#    cgroups-mount && screen -dmS docker_daemon dockerd -D && docker info
