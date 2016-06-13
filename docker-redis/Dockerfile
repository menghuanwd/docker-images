FROM        ubuntu:14.04

MAINTAINER  menghuanwd "651019063@qq.com"

ENV REFRESHED_AT 2016-05-23

RUN         apt-get update

RUN         apt-get install -y redis-server

EXPOSE      6379

ENTRYPOINT   ["/usr/bin/redis-server"]