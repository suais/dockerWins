# **Docker安装cassandra** #
## 服务简介 ##

 <img src="./../images/cassandra.jpg" width = "420" alt="Github" align=center />

* * *
Apache Cassandra是一个开源的分布式数据库管理系统，旨在处理许多商品服务器上的大量数据，提供没有单一故障点的高可用性。Cassandra为跨越多个数据中心的集群提供强大的支持，其异步无主复制允许所有客户进行低延迟操作。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />
 
[ Github ](https://github.com/apache/cassandra)
## 准备镜像 ##
    docker pull cassandra
## 运行容器 ##
创建network

    docker network create cassandra-network

创建容器

    docker run --name some-cassandra --network cassandra-network -d cassandra

连接CQL

    docker run -it --network cassandra-network --rm cassandra cqlsh some-cassandra
#### 参数说明 ####
`--network cassandra-network`：指定网络环境为自定义网络