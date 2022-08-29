FROM jitpack/tools

MAINTAINER jitpack <jitpack@jitpack.io>

ENV ANDROID_SDK /opt/android-sdk-linux
ENV ANDROID_HOME /opt/android-sdk-linux
ENV ANDROID_SDK_HOME /opt/android-sdk-linux
ENV ANDROID_SDK_ROOT /opt/android-sdk-linux
WORKDIR /opt

RUN dpkg --add-architecture i386 && \
	apt-get -qqy update && \
    apt-get -qqy install -y libc6:i386 libncurses5:i386 libstdc++6:i386 lib32z1 expect make xvfb firefox && \
    apt-get clean && \
    apt-get autoremove -y

RUN wget -q https://dl.google.com/android/repository/sdk-tools-linux-4333796.zip -O android-sdk-tools.zip && \
    unzip -q android-sdk-tools.zip -d ${ANDROID_HOME} && \
    rm android-sdk-tools.zip

ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/tools/bin:${ANDROID_HOME}/platform-tools

RUN mkdir -p ~/.android/ && touch ~/.android/repositories.cfg

RUN yes | sdkmanager --licenses
RUN sdkmanager "tools" "platform-tools"

RUN yes | sdkmanager \
    "ndk-bundle" \
    "build-tools;28.0.0" \
    "extras;android;m2repository" \
    "extras;google;m2repository" \
    "extras;google;google_play_services" \
    "extras;m2repository;com;android;support;constraint;constraint-layout;1.0.2" \
    "extras;m2repository;com;android;support;constraint;constraint-layout;1.0.1"

RUN chown -R jitpack:jitpack ${ANDROID_HOME} && \
    cd  /opt/android-sdk-linux/ndk-bundle/toolchains && \
    ln -s aarch64-linux-android-4.9 mips64el-linux-android && \
    ln -s arm-linux-androideabi-4.9 mipsel-linux-android
    
