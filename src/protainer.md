# Docker安装portainer #
## 服务简介 ##

<img src="./../images/portainer.png" width = "420" alt="Github" align=center />

* * *


Portainer是Docker的图形化管理工具，提供状态显示面板、应用模板快速部署、容器镜像网络数据卷的基本操作(包括上传下载镜像，创建容器等操作)、事件日志显示、容器控制台操作、Swarm集群和服务等集中管理和操作、登录用户管理和控制等功能。功能十分全面，基本能满足中小型单位对容器管理的全部需求。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />

[prometheus GitHub](https://github.com/portainer/portainer)

## 准备镜像 ##
    docker pull portainer/portainer
## 运行容器 ##
    docker run -d \
    -p 9000:9000 \
    --restart=always \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v /portainer_data:/data \
    --name prtainer portainer/portainer \
## 常见说明 ##
`访问地址`:localhost:9000
首次登陆需要注册用户和密码