FROM ruby:2.3.1

MAINTAINER  menghuanwd "651019063@qq.com"

RUN gem install --no-ri --no-rdoc sinatra redis

RUN mkdir -p /opt/webapp

EXPOSE 4567

CMD ["/opt/webapp/bin/webapp"]

