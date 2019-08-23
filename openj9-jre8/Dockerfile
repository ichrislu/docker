FROM chrislu8468/alpine:1.0

MAINTAINER Chris <chrislu.name@gmail.com>

# 安装glibc
COPY glibc-2.27-r0.apk .
RUN apk add --update && \
        apk add --allow-untrusted glibc-2.27-r0.apk && \
        rm -fr glibc-2.27-r0.apk && \
        rm -rf /var/cache/apk/*

# 安装JDK
# 使用ADD替换COPY，因为ADD支持解压
ADD OpenJDK8U-jre_x64_linux_openj9_8u222b10_openj9-0.15.1.tar.gz /usr/

# 设置环境变量
ENV JAVA_HOME /usr/jdk8u222-b10-jre
ENV PATH $PATH:$JAVA_HOME/bin
