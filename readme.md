# Docker Images

docker run --name kibana -e ELASTICSEARCH_URL=http://192.168.99.102:9201 -p 5601:5601 -d kibana

docker run --name elasticsearch_head_ik -p 9200:9200 -p 9300:9300 -d menghuanwd/elasticsearch_head_ik

curl -XPOST http://192.168.99.102:9200/index/fulltext/_mapping -d'
{
    "fulltext": {
             "_all": {
            "analyzer": "ik_max_word",
            "search_analyzer": "ik_max_word",
            "term_vector": "no",
            "store": "false"
        },
        "properties": {
            "content": {
                "type": "string",
                "store": "no",
                "term_vector": "with_positions_offsets",
                "analyzer": "ik_max_word",
                "search_analyzer": "ik_max_word",
                "include_in_all": "true",
                "boost": 8
            }
        }
    }
}'

curl -XPOST http://192.168.99.102:9200/index/fulltext/1 -d'
{"content":"美国留给伊拉克的是个烂摊子吗"}
'
