FROM jitpack/tools

MAINTAINER jitpack <jitpack@jitpack.io>

WORKDIR /opt

ENV ANDROID_HOME /opt/android-sdk-linux

RUN dpkg --add-architecture i386 && \
	apt-get update && \
    apt-get install -y libc6:i386 libncurses5:i386 libstdc++6:i386 lib32z1 expect && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get autoremove -y && \
    apt-get clean

RUN curl -sL http://dl.google.com/android/android-sdk_r24.3.4-linux.tgz | gunzip | tar -x -C /opt

ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools
ENV ANDROID_BUILD_TOOLS_VERSION 23.0.2

COPY accept-licenses.sh /opt/
RUN /opt/accept-licenses.sh "android update sdk --no-ui -a --filter tools,extra-android-support,extra-android-m2repository,extra-google-m2repository,extra-google-google_play_services,build-tools-${ANDROID_BUILD_TOOLS_VERSION}"

