ARG GRADLE_VERSION
FROM nao20010128nao/android-build:sdk-gradle-${GRADLE_VERSION}
MAINTAINER nao20010128nao
ARG ANDROID_NDK_VERSION=13b
ARG ANDROID_CMAKE_VERSION=3.6.3155560

ENV ANDROID_NDK_HOME=/opt/android-ndk
ENV PATH=${PATH}:${ANDROID_NDK_HOME}:${ANDROID_HOME}/cmake/bin

RUN set -x && apt-get update -qq && apt upgrade -y -qq && apt-get clean && rm -rf /var/lib/apt/lists/* && \

    mkdir /opt/android-ndk-tmp && \
    cd /opt/android-ndk-tmp && wget -q https://dl.google.com/android/repository/android-ndk-r${ANDROID_NDK_VERSION}-linux-x86_64.zip && \
    unzip -q android-ndk-r${ANDROID_NDK_VERSION}-linux-x86_64.zip && mv ./android-ndk-r${ANDROID_NDK_VERSION} ${ANDROID_NDK_HOME} && \
    rm -rf /opt/android-ndk-tmp && \

    mkdir /opt/android-cmake-tmp && \
    cd /opt/android-cmake-tmp && wget -q https://dl.google.com/android/repository/cmake-${ANDROID_CMAKE_VERSION}-linux-x86_64.zip -O android-cmake.zip && \
    unzip -q android-cmake.zip -d android-cmake && mv ./android-cmake ${ANDROID_HOME}/cmake && \
    rm -rf /opt/android-cmake-tmp
