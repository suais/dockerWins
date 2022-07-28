# **Docker安装Hive** #
## 服务简介 ##

 <img src="./../images/hive.png" width = "420" alt="Github" align=center />

* * *

Apache Hive是一个构建于Hadoop顶层的数据仓库，可以将结构化的数据文件映射为一张数据库表，并提供简单的SQL查询功能，可以将SQL语句转换为MapReduce任务进行运行。需要注意的是，Hive它并不是数据库。


Hive依赖于HDFS和MapReduce，其对HDFS的操作类似于SQL，我们称之为HQL，它提供了丰富的SQL查询方式来分析存储在HDFS中的数据。HQL可以编译转为MapReduce作业，完成查询、汇总、分析数据等工作。这样一来，即使不熟悉MapReduce 的用户也可以很方便地利用SQL 语言查询、汇总、分析数据。而MapReduce开发人员可以把己写的mapper 和reducer 作为插件来支持Hive 做更复杂的数据分析。


 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />
 
[ Github ](https://github.com/apache/hive)
## 准备镜像 ##下·
## 运行容器 ##
#### 参数说明 ####