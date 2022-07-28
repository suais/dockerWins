# **Docker安装Hadoop** #
## 服务简介 ##

 <img src="./../images/hadoop.png" width = "420" alt="Github" align=center />

* * *
Apache Hadoop是一款支持数据密集型分布式应用程序并以Apache 2.0许可协议发布的开源软件框架，有助于使用许多计算机组成的网络来解决数据、计算密集型的问题。基于MapReduce计算模型，它为大数据的分布式存储与处理提供了一个软件框架。所有的Hadoop模块都有一个基本假设，即硬件故障是常见情况，应该由框架自动处理。

Apache Hadoop的核心模块分为存储和计算模块，前者被称为Hadoop分布式文件系统（HDFS），后者即MapReduce计算模型。Hadoop框架先将文件分成数据块并分布式地存储在集群的计算节点中，接着将负责计算任务的代码传送给各节点，让其能够并行地处理数据。这种方法有效利用了数据局部性，令各节点分别处理其能够访问的数据。与传统的超级计算机架构相比，这使得数据集的处理速度更快、效率更高。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />
 
[ Github ](https://github.com/apache/hadoop)
## 准备镜像 ##
    docker pull sequenceiq/hadoop-docker
## 运行容器 ##
    docker run -i -t --network host  \
    -p 50070:50070 \
    -p 9000:9000 \
    -p 8088:8088 \
    -p 8040:8040 \
    -p 8042:8042  \
    -p 49707:49707  \
    -p 50010:50010  \
    -p 50075:50075 \
    -p 50090:50090 \
    sequenceiq/hadoop-docker /etc/bootstrap.sh -bash

#### 参数说明 ####