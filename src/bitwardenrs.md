# Docker安装bitwardenrs #
## 服务简介 ##
一款开源免费的密码的管理器，作为密码管理软件，Bitwarden可以集中存储，加密，生成我们在各个网站的用户名和密码并在对应的网站自动填写。

[bitwardenrs github](https://github.com/bitwarden/server)
## 准备镜像 ##

    docker pull bitwardenrs/server

## 运行容器 ##
    
    docker run -d 
    --name bitwardenrs
    --restart unless-stopped 
    -v /docker_volume/bitwarden/data/:/data/ 
    -p 80:80 
    bitwardenrs/server

## 常见说明 ##

- `-v`:挂载容器数据目录至宿主机，此处应填写为自己的目录
- `-p`:默认映射80端口，可以修改为自己需要的端口