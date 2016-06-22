FROM phusion/baseimage

MAINTAINER  menghuanwd "651019063@qq.com"

CMD ["/sbin/my_init"]

RUN apt-get update && apt-get -y upgrade

RUN apt-get install -y gcc make g++ build-essential libc6-dev tcl git

RUN git clone https://github.com/antirez/redis.git

RUN (cd /redis && make)

ADD ./redis.conf /redis/redis.conf

ADD ./start.sh /start.sh

RUN chmod 755 /start.sh

RUN mkdir /data

EXPOSE 6379

CMD ["/bin/bash", "/start.sh"]
