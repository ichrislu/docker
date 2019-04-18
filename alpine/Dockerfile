FROM alpine:3.7

MAINTAINER Chris <chrislu.name@gmail.com>

RUN apk add -U tzdata \
	&& cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
	&& apk del tzdata
RUN echo "Asia/Shanghai" > /etc/timezone