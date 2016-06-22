#elasticsearch with head and ik

FROM        elasticsearch

MAINTAINER  menghuanwd "651019063@qq.com"

RUN         /usr/share/elasticsearch/bin/plugin install mobz/elasticsearch-head

ENV         ES_IK_VERSION 1.9.3

RUN         curl -o elasticsearch-analysis-ik-${ES_IK_VERSION}.zip -L -e  '; auto' https://github.com/medcl/elasticsearch-analysis-ik/releases/download/v${ES_IK_VERSION}/elasticsearch-analysis-ik-${ES_IK_VERSION}.zip && mkdir -p /usr/share/elasticsearch/plugins/ik/ && unzip elasticsearch-analysis-ik-${ES_IK_VERSION}.zip -d /usr/share/elasticsearch/plugins/ik/ && rm -f elasticsearch-analysis-ik-${ES_IK_VERSION}.zip

EXPOSE 9200 9300

# docker build -t menghuanwd/elasticsearch_head_ik .

# docker run --name elasticsearch_head_ik -p 9200:9200 -p 9300:9300 -d menghuanwd/elasticsearch_head_ik
