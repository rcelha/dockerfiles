FROM java:jdk
USER root

ENV DEBIAN_FRONTEND noninteractive

RUN dpkg --add-architecture i386 && \
    apt-get update && \
    apt-get install -yq libstdc++6:i386 zlib1g:i386 libncurses5:i386 ant maven --no-install-recommends && \
    apt-get autoremove && \
    apt-get autoclean;

# Gradle
ENV GRADLE_URL http://services.gradle.org/distributions/gradle-2.2.1-all.zip
RUN curl -L ${GRADLE_URL} -o /tmp/gradle-2.2.1-all.zip && unzip /tmp/gradle-2.2.1-all.zip -d /usr/local && rm /tmp/gradle-2.2.1-all.zip
ENV GRADLE_HOME /usr/local/gradle-2.2.1

# Android SDK
ENV ANDROID_SDK_VERSION 24.4.1
ENV ANDROID_SDK_URL http://dl.google.com/android/android-sdk_r${ANDROID_SDK_VERSION}-linux.tgz
ENV ANDROID_HOME /usr/local/android-sdk-linux
RUN curl -L ${ANDROID_SDK_URL} | tar xz -C /usr/local

# Install Android SDK componentsa
# SDK + Tools + platformtools
ENV ANDROID_BUILD_TOOLS_VERSION 23.0.1
ENV ANDROID_SDK_VERSION 23
ENV ANDROID_SDK_COMPONENTS platform-tools,build-tools-${ANDROID_BUILD_TOOLS_VERSION},android-${ANDROID_SDK_VERSION},extra-android-support
RUN  ( sleep 5 && while [ 1 ]; do sleep 1; echo y; done ) | ${ANDROID_HOME}/tools/android update sdk --no-ui --all --filter "${ANDROID_SDK_COMPONENTS}"

# Path
ENV PATH $PATH:${ANDROID_HOME}/tools:$ANDROID_HOME/platform-tools:${GRADLE_HOME}/bin
