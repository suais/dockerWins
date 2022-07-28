# **Docker in Docker** #
## 服务简介 ##
 <img src="./../images/docker.png" width = "420" alt="Github" align=center />

* * *
## 准备镜像 ##
    docker pull docker
## 运行容器 ##
创建一个network

    docker network create some-network

创建Volume

    docker volume create some-docker-certs-ca
    docker volume create some-docker-certs-client

运行容器

    docker run --privileged --name some-docker -d --network some-network --network-alias docker -e DOCKER_TLS_CERTDIR=/certs -v some-docker-certs-ca:/certs/ca -v some-docker-certs-client:/certs/client docker
#### 参数说明 ####