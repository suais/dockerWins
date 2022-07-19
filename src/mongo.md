# Docker安装mongo #
## 服务简介 ##
MongoDB是专为可扩展性，高性能和高可用性而设计的数据库。它可以从单服务器部署扩展到大型、复杂的多数据中心架构。利用内存计算的优势，MongoDB能够提供高性能的数据读写操作。 MongoDB的本地复制和自动故障转移功能使您的应用程序具有企业级的可靠性和操作灵活性。
## 准备镜像 ##
    docker pull mongo
## 运行容器 ##
    docker run -d \
    --name mongo \
    --restart=always \
    -v /docker_vloume/mongodb/data:/data/db \
    -p 28018:27017 \
    --privileged=true mongo
## 常见说明 ##
