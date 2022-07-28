# **Docker安装Nats** #
## 服务简介 ##


<img src="./../images/nats.png" width = "420" alt="Github" align=center />

* * *
nats是一个开源的，云原生的消息系统。Apcera，百度，西门子，VMware，HTC和爱立信等公司都有在使用。

核心基于EventMachine开发，原理是基于消息发布订阅机制，每台服务器上的每个模块会根据自己的消息类别向MessageBus发布多个消息主题，而同时也向自己需要交互的模块，按照需要的主题订阅消息。能够达到每秒8-11百万个消息，整个程序很小只有3M Docker image，它不支持持久化消息，如果你离线，你就不能获得消息。使用nats streaming可以做到持久化，缓存等功能。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />

[ Github ](https://github.com/nats-io/nats-server)
## 准备镜像 ##
    docker pull nats
## 运行容器 ##
#### 参数说明 ####