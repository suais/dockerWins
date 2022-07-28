# **Docker安装couchdb** #
## 服务简介 ##

 <img src="./../images/couchdb.jpg" width = "420" alt="Github" align=center />

* * *

CouchDB 是众多称作 NoSQL 解决方案中的一员。与众不同的是，CouchDB 是一个面向文档的数据库，在它里面所有文档域（Field）都是以键值对的形式存储的。域（Field）可以是一个简单的键值对、列表或者是 map。

CouchDB 会为存储到数据库中的每一个文档分配一个文档级别的唯一标识符（_id），同时每次将变动保存到数据库中时还会分配一个修订号（_rev）。

NoSQL 数据库的出现代表着传统的关系型数据库的转变，它能够提供很多好处，当然其自身也面临着挑战。CouchDB 为我们提供了下面的特性：

容易地在多个服务器实例之间进行数据库复制
快速地索引和检索
REST 风格的文档插入、更新、检索和删除的接口
基于 JSON 的文档格式（更容易地在不同语言之间转换）
为用户选择的语言提供多个库（指一些流行的语言）
通过 _changes 订阅数据更新
从 NoSQL 系统可视化向导中可以找到一个非常出色的工具，它能帮你决定哪一个数据存储适合你。该指南描述了选择数据库系统时应该关注的三个方面（NoSQL 和关系型数据库都是如此）。在我们的项目中使用该指南筛选数据库时会关注下面的特性：

可用性
一致性
分区容忍度
CouchDB 侧重于 AP（可用性和分区容忍度），这正是满足我们的数据关注点所要寻找的数据库（更不用说在连续的或者点对点的设备间进行数据复制的能力）。相比之下，MongoDB 侧重于 CP（一致性和分区容忍度），像 Neo4J 这样的数据库则提供了特有的面向图形的结构。

另一个出色的工具是这篇博客文章，它对 Cassandra、MongoDB、CouchDB、Redis、Riak、Hbase 和 Membase 做了比较。

当然，对于一个给定的项目你很可能有多个工具，换言之，这就需要明确需求并找到合适的工具以满足这些需求。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />
 
[ Github ](https://github.com/apache/couchdb)
## 准备镜像 ##
    docker pull couchdb
## 运行容器 ##
    docker run -d --name my-couchdb -p 5984:5984 couchdb
#### 参数说明 ####