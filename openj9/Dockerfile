FROM chris-alpine:1.0

MAINTAINER Chris <chrislu.name@gmail.com>

# 安装glibc
COPY glibc-2.27-r0.apk .
RUN apk add --update && \
        apk add --allow-untrusted glibc-2.27-r0.apk && \
        rm -fr glibc-2.27-r0.apk && \
        rm -rf /var/cache/apk/*

# 添加libz(after jdk10)
COPY libz/usr/lib/libz.so* /usr/glibc-compat/lib/

# 添加gcc-lib(after jdk10)
COPY gcc-lib/usr/lib/libgcc* /usr/glibc-compat/lib/
COPY gcc-lib/usr/lib/libstdc++* /usr/glibc-compat/lib/

# 安装JDK
# 使用ADD替换COPY，因为ADD支持解压
ADD OpenJDK11U-jdk_x64_linux_openj9_jdk-11.0.1_13_openj9-0.11.0_11.0.1_13.tar.gz /usr/

# 设置环境变量
ENV JAVA_HOME /usr/jdk-11.0.1+13
ENV PATH $PATH:$JAVA_HOME/bin