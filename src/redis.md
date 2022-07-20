# Docker安装redis #
## 服务简介 ##

<img src="./../images/redis.jpg" width = "420" alt="Github" align=center />

* * *


redis是一个开源的、内存型的、支持多种数据结构的存储系统，常用来做缓存、数据库、消息代理，除此之外，它还支持数据持久化存储，支持集群化的协同方式。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />

[redis GitHub](https://github.com/redis/redis)

## 准备镜像 ##
    docker pull redis
## 运行容器 ##

    docker run --name redis 
    -p 6379:6379 
    -v /redis/data:/data 
    -v /redis/conf/redis.conf:/etc/redis/redis.conf 
    -d redis redis-server /etc/redis/redis.conf 

## 常见说明 ##
启动前需要先创建Redis外部挂载的配置文件 （ /home/redis/conf/redis.conf ）

    mkdir /redis/conf
    touch /redis/conf/redis.conf

