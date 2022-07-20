# Docker安装rockerChat #
## 服务简介 ##


<img src="./../images/rocketchat.jpg" width = "420" alt="Github" align=center />

* * *


RocketChat是一款优秀的开源聊天软件。支持各种平台，IOS、Android、Web、Mac、Windows以及Linux，安装部署简单，功能简单易用，目前部分功能还在完善当中，特别适合小公司自建聊天平台。项目开源地址 ，项目[官方站点](https://rocket.ch)

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />


[ RockerChat Github](https://github.com/RocketChat)
## 准备镜像 ##
获取docker-compose文件

    curl -L https://raw.githubusercontent.com/RocketChat/Rocket.Chat/develop/docker-compose.yml -o \docker-compose.yml

## 运行容器 ##
    docker-compose up -d
## 常见说明 ##
`访问地址`:localhost:3000，默认为3000端口，可在yml文件中进行修改。