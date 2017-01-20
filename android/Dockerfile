FROM jitpack/tools

MAINTAINER jitpack <jitpack@jitpack.io>

WORKDIR /opt

RUN dpkg --add-architecture i386 && \
	apt-get update && \
    apt-get install -y libc6:i386 libncurses5:i386 libstdc++6:i386 lib32z1 expect && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get autoremove -y && \
    apt-get clean

RUN curl -sL http://dl.google.com/android/android-sdk_r24.3.4-linux.tgz | gunzip | tar -x -C /opt

ENV ANDROID_HOME /opt/android-sdk-linux
ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools
ENV API_LEVELS android-18,android-19,android-20,android-21,android-22,android-23,android-24,android-25
ENV BUILD_TOOLS=build-tools-25,build-tools-25.0.3

COPY accept-licenses.sh /opt/

RUN /opt/accept-licenses.sh "android update sdk --no-ui -a --filter tools,platform-tools,${API_LEVELS},extra-android-support,extra-android-m2repository,extra-google-m2repository,extra-google-google_play_services,${BUILD_TOOLS}"
