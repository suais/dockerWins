# Docker安装guacamole #
## 服务简介 ##

 <img src="./../images/guacamole.png" width = "420" alt="Github" align=center />

* * *


Apache Guacamole（鳄梨酱）是一个基于HTML5 Web应用程序，可以随时通过浏览器连接已经配置好的机器，它支持标准协议，例如VNC、RDP和SSH。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />


[guacamole Github](https://github.com/bitwarden/server)
## 准备镜像 ##
第一个镜像

    docker pull guacamole/guacd

第二个镜像

    docker pull guacamole/guacamole


## 运行容器 ##

部署Guacd，Guacd是Apache Guacamole网络应用程序使用的本地服务器端代理，运行Guacd：

    docker run --name guacd -d guacamole/guacd

部署Guacdmole

    
    docker run --name guacamole  \
    --link guacd \
    -e MYSQL_HOSTNAME=192.168.0.1 \
    -e MYSQL_PORT=3306 \
    -e MYSQL_DATABASE=guacamole \ 
    -e MYSQL_USER='guacamole' \
    -e MYSQL_PASSWORD=guacamole  \
    -d -p 8080:8080 \
    guacamole/guacamole

## 常见说明 ##
- `-e MYSQL_HOSTNAME`: MYSQL数据库地址
- `-e MYSQL_PORT=3306`: 端口
- `-e MYSQL_DATABASE=guacamole`：填写数据库名称
- `-e MYSQL_USER='guacamole'`：填写用户名
- `-e MYSQL_PASSWORD=guacamole`：数据库密码

安装容器需要准备MYSQL数据库，Guacamole程序不会自动初始化数据库，运行MySQL之后需要手动初始化数据库，而Guacamole提供了数据库文件，只需要生成导入就可以。

    docker run --rm guacamole/guacamole /opt/guacamole/bin/initdb.sh --mysql > initdb.sql

将生成的initdb.sql文件在MySQL中执行，生成表结构
运行成功后，通过浏览器访问：localhost:8080/guacamole

- `访问地址`:localhost:8080