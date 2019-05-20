#ベースはCentOS7
FROM centos:centos7

#必要なソフトウェアをインストール
RUN yum install -y java wget

#ユーザ「elasticsearch」を追加
RUN groupadd -g 1000 elasticsearch && \
    adduser -u 1000 -g 1000 -d /usr/share/elasticsearch elasticsearch

USER elasticsearch
WORKDIR /usr/share/elasticsearch

#Elasticsearch7のダウンロード
RUN wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.0.1-linux-x86_64.tar.gz \
  && tar zxvf elasticsearch-7.0.1-linux-x86_64.tar.gz

#Elasticsearchの初期設定
RUN echo -e $"\n\
network.host: 0.0.0.0\n\
discovery.type: single-node\n\
" >> /usr/share/elasticsearch/elasticsearch-7.0.1/config/elasticsearch.yml

#コンテナ起動時にElasticsearchをフォアグラウンドで起動
CMD ["/usr/share/elasticsearch/elasticsearch-7.0.1/bin/elasticsearch"]

EXPOSE 9200
