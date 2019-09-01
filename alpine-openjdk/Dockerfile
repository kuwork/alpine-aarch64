FROM kuwork/alpine:3.10.2-aarch64

ARG BUILD_DATE
ARG VCS_REF
ENV TIMEZONE Asia/Shanghai
ENV JAVA_HOME /usr/lib/jvm/default-jvm

LABEL maintainer="kuwork <kuwork@126.com>" \
    architecture="arm64v8/aarch64" \
    openjdk-version="8.212.04-r1" \
    alpine-version="3.10.2" \
    build="31-Aug-2019" \
    org.opencontainers.image.title="alpine-openjdk" \
    org.opencontainers.image.description="Openjdk Docker image running on Alpine Linux" \
    org.opencontainers.image.authors="kuwork <kuwork@126.com>" \
    org.opencontainers.image.vendor="K.W. Systems" \
    org.opencontainers.image.version="v8.212.04-r1" \
    org.opencontainers.image.source="https://github.com/kuwork/alpine-aarch64" \
    org.opencontainers.image.revision=$VCS_REF \
    org.opencontainers.image.created=$BUILD_DATE

RUN apk add --no-cache openjdk8 curl busybox tzdata && \
    cp /usr/share/zoneinfo/${TIMEZONE}  /etc/localtime && \
    echo "${TIMEZONE}" > /etc/timezone && \
    rm -rf /tmp/* /var/cache/apk/* && \
    ln -sf "${JAVA_HOME}/bin/"* "/usr/bin/"
