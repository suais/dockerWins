# **Docker安装Traefik** #
## 服务简介 ##

<img src="./../images/traefik.png" width = "420" alt="Github" align=center />

* * *

Traefik 是一款 open-source 边缘路由器，可让您轻松地发布服务. 它接收来自您的系统请求，并找出负责处理它们的后端服务组件。

traefik 与众不同在于它能够自动发现适合您服务的配置。 当 Traefik 检查您的基础设施时，它会发现相关信息，并发现哪个服务服务于哪个请求。

使用 Traefik，无需维护和同步配置文件：所有操作都会自动实时完成（无重启，不用中断服务）。 使用 Traefik，您只需花时间于系统开发和部署新功能，而不是配置和维护其工作状态。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />
 
[ GitHub ](https://github.com/traefik/traefik)
## 准备镜像 ##
    docker pull traefik
## 运行容器 ##
#### 参数说明 ####