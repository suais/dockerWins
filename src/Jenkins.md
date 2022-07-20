# Docker安装jenkins #
## 服务简介 ##

 <img src="./../images/jenkins.png" width = "420" alt="Github" align=center />

* * *


Jenkins是一个独立的开源软件项目，是基于Java开发的一种持续集成工具，用于监控持续重复的工作，旨在提供一个开放易用的软件平台，使软件的持续集成变成可能。前身是Hudson是一个可扩展的持续集成引擎。可用于自动化各种任务，如构建，测试和部署软件。Jenkins可以通过本机系统包Docker安装，甚至可以通过安装Java Runtime Environment的任何机器独立运行。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />
 
[jenkins Github](https://github.com/jenkinsci/jenkins)
## 准备镜像 ##
    docker pull jenkins/jenkins
## 运行容器 ##
    docker run -d \
    -p 8080:8080 \
    -p 50000:50000 \
    -v /docker_volume/var/jenkins:/var/jenkins_home  \
    -v /etc/localtime:/etc/localtime \
    --restart=always \
    --name=jenkins jenkins/jenkins 
## 常见说明 ##
`-v /etc/localtime:/etc/localtime`是为了让容器使用和服务器同样的时间设置

管理员的初始密码在 Jenkins的工作目录,使用以下命名查看：
    
    cat /docker_volume/var/jenkins/secrets/initialAdminPassword
- `访问地址`:localhost:8080

