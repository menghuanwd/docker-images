FROM        ubuntu:14.04

MAINTAINER  menghuanwd "651019063@qq.com"

ENV REFRESHED_AT 2016-05-23

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

RUN    apt-get update

RUN    apt-get install -y git

RUN    apt-get install -y build-essential libssl-dev libreadline-dev zlib1g-dev curl git

RUN    git clone git://github.com/sstephenson/rbenv.git ~/.rbenv

RUN    git clone git://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build

RUN    git clone git://github.com/sstephenson/rbenv-gem-rehash.git ~/.rbenv/plugins/rbenv-gem-rehash

RUN    git clone git://github.com/rkh/rbenv-update.git ~/.rbenv/plugins/rbenv-update

RUN    git clone git://github.com/AndorChen/rbenv-china-mirror.git ~/.rbenv/plugins/rbenv-china-mirror

RUN    echo 'export PATH="~/.rbenv/bin:$PATH"' >> ~/.bashrc

RUN    echo 'eval "$(rbenv init -)"' >> ~/.bashrc

RUN    source ~/.bashrc

RUN    ~/.rbenv/bin/rbenv install 2.3.0

RUN    ~/.rbenv/bin/rbenv global 2.3.0

#RUN    ~/.rbenv/bin/rbenv shell 2.3.0
RUN     echo 'ruby -v'

RUN    ~/.rbenv/shims/gem install bundler --no-ri --no-rdoc

CMD ["/bin/bash"]

# docker build -t rbenv .