# 说明

本仓库是自己创建的基础镜像仓库

### alpine

基础镜像，基于alpine3.7版，修改记录

1. 配置时区：/etc/timezone
2. 配置时间：/etc/localtime

### openj9-jdk11

基于chris-alpine基础镜像，兼容性测试版本alpine 3.6

1. 添加c语言运行库：glibc-2.27-r0，下载glibc-2.27-r0.apk保存到Dockerfile同级目录
2. 添加libz（jdk10以后需要的）：下载zlib.tar.xz，解压到Dockerfile同级目录
3. 添加gcc-lib（jdk10以后需要的）：下载gcc-libs.tar.xz后，解压到Dockerfile同级目录
4. 安装JDK11
5. 设置环境变量

### openj9-jre8

1. 添加c语言运行库，glibc-2.27-r0，下载glibc-2.27-r0.apk保存到Dockerfile同级目录
2. 安装JDK8
3. 设置环境变量

### TODO

1. chris-tomcat，解决JVM时区问题
2. chris-nginx，基于nginx:*-alpine，与chris-alpine同样方法解压时区问题
3. chris-tomcat，基于chris-openj8，安装tomcat，设置环境变量（ENV JAVA_TOOL_OPTIONS=-Duser.timezone=GMT+08、ENV CATALINA_HOME /eyas/apache-tomcat-8.5.35、ENV PATH $CATALINA_HOME/bin:$PATH）、删除没用的Tomcat默认目录，设置bin目录执行权限