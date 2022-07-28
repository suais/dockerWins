# Docker安装Postgresql #
## 服务简介 ##

<img src="./../images/postgresql.png" width = "420" alt="Github" align=center />

* * *

PostgreSQL是一个功能强大的开源对象关系型数据库系统，他使用和扩展了SQL语言，并结合了许多安全存储和扩展最复杂数据工作负载的功能。PostgreSQL的起源可以追溯到1986年，作为加州大学伯克利分校POSTGRES项目的一部分，并且在核心平台上进行了30多年的积极开发。

PostgresSQL凭借其经过验证的架构，可靠性，数据完整性，强大的功能集，可扩展性以及软件背后的开源社区的奉献精神赢得了良好的声誉，以始终如一地提供高性能和创新的解决方案。PostgreSQL在所有主要操作系统开始使用PostgreSQL从未如此简单。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />

[postgresql Git](https://git.postgresql.org/gitweb/?p=postgresql.git)

## 准备镜像 ##
    docker pull postgres
## 运行容器 ##
    docker run \
    --name postgres \
    -e POSTGRES_PASSWORD=password \
    -p 5432:5432 
    -v /usr/local/postgresql/data:/var/lib/postgresql/data 
    -d postgres
## 常见说明 ##