# **Docker安装elasticsearch** #
## 服务简介 ##

 <img src="./../images/elastic.jpg" width = "420" alt="Github" align=center />

* * *
Elasticsearch 是一个分布式的免费开源搜索和分析引擎，适用于包括文本、数字、地理空间、结构化和非结构化数据等在内的所有类型的数据。Elasticsearch 在 Apache Lucene 的基础上开发而成，由 Elasticsearch N.V.（即现在的 Elastic）于 2010 年首次发布。Elasticsearch 以其简单的 REST 风格 API、分布式特性、速度和可扩展性而闻名，是 Elastic Stack 的核心组件；Elastic Stack 是一套适用于数据采集、扩充、存储、分析和可视化的免费开源工具。人们通常将 Elastic Stack 称为 ELK Stack（代指 Elasticsearch、Logstash 和 Kibana），目前 Elastic Stack 包括一系列丰富的轻量型数据采集代理，这些代理统称为 Beats，可用来向 Elasticsearch 发送数据。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />
 
[ Github ](https://github.com/elastic/elasticsearch)
## 准备镜像 ##
    docker pull elasticsearch
    docker pull mobz/elasticsearch-head:5
## 运行容器 ##
    docker run -d --name es -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" b0e9f9f047e6

安装 ik 分词器

    docker exec -it es bash ./bin/elasticsearch-plugin install https://github.com/medcl/elasticsearch-analysis-ik/releases/download/v7.1.1/elasticsearch-analysis-ik-7.1.1.zip

安装完毕之后输入：exit退出容器。
安装 ik 分词器后重启 Elasticsearch

    docker restart es

安装 es-head

    docker start elasticsearch-head

es-head 连接 Elasticsearch

    docker exec -it es /bin/bash
    vi config/elasticsearch.yml
    # 添加如下两条配置，注意冒号后面有空格，保存并退出
    http.cors.enabled: true 
    http.cors.allow-origin:

最后退出容器，并重启 Elasticsearch

    exit
    docker restart es

#### 参数说明 ####