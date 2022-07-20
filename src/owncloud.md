# Docker安装owncloud #
## 服务简介 ##

<img src="./../images/owncloud.png" width = "420" alt="Github" align=center />

* * *

OwnCloud 一款文件主机服务软件，就是我们平时使用的云存储，不过这是在自己主机的服务器上建立属于自己的私有云，OwnCloud　使用AGPLv3协议发布。本项目是基于PHP和SQLite，MySQL，Oracle或PostgreSQL数据库，所以它可以运行在所有的平台上。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />

[owncloud GitHub](https://github.com/docker-library/owncloud)
## 准备镜像 ##

    docker pull owncloud/server

## 运行容器 ##
    docker run \
    --restart unless-stopped  \
    -e OWNCLOUD_DOMAIN=localhost:8080    \
    -e OWNCLOUD_ADMIN_USERNAME=admin   \
    -e OWNCLOUD_ADMIN_PASSWORD=admin \
    -p 8080:8080  
    -v /docker_vloume/owncloud:/mnt/data   \
    --name owncloud   \
    -d owncloud/server
## 常见说明 ##
- `-e OWNCLOUD_DOMAIN`: 配置访问地址
- `-e OWNCLOUD_ADMIN_USERNAME`：配置默认管理员账号
- `-e OWNCLOUD_ADMIN_PASSWORD`：配置自己的管理员密码
- `访问地址`:localhost:8080