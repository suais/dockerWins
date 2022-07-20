# Docker安装omniDB #
## 服务简介 ##

<img src="./../images/omnidb.png" width = "420" alt="Github" align=center />

* * *


OmniDB是一个基于浏览器的工具，它简化了专注于交互性的数据库管理，旨在实现在Web端强大的数据库管理功能且是轻量级的，目前支持PostgreSQL、Oracle、MySQL / MariaDB，未来应该会支持Firebird、 SQLite、Microsoft SQL Server、IBM DB2等数据库.

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />

[omniDB GitHub](https://github.com/OmniDB/OmniDB)

## 准备镜像 ##
    docker pull taivokasper/omnidb
## 运行容器 ##
    docker run -it \
    -v config-omnidb:/etc/omnidb \
    -p 8080:8080 \
    -p 25482:25482 \
    --name omnidb taivokasper/omnidb
## 常见说明 ##
- 需要注意的是，如果你要连接的数据库是容器的话，那么你直接输入主机地址为localhost会弹出下面的错误信息:

    Can't content to mysql ....

- omniDB容器部署好之后的默认账号和密码都是admin,请登录后在后台进行修改密码。
- `访问地址`:localhost:8080