# Docker安装pgadmin4 #

## 服务简介 ##
pgAdmin4 是开源数据库 PostgreSQL 的图形管理工具，是桌面版图形管理工具pgAdmin3 的重写，遵循 PostgreSQL协议 是开源、免费、可商用的。pgAdmin4 是python开发的web应用程序，既可以部署为web模式通过浏览器访问，也可以部署为桌面模式独立运行。

[pgadmin4 Git](https://github.com/postgres/pgadmin4)

## 准备镜像 ##
    docker pull dpage/pgadmin4
## 运行容器 ##
	docker run  -d \
    --name pgadmin -p 80:80 \
    -e PGADMIN_DEFAULT_EMAIL=admin@qq.com \
    -e PGADMIN_DEFAULT_PASSWORD=123456 \
	-v /docker_vloume/pgadmin/data:/var/lib/pgadmin \
	-v /docker_vloume/pgadmin/logs:/var/log/pgadmin \
    dpage/pgadmin4
## 常见说明 ##
- `-e PGADMIN_DEFAULT_EMAIL=admin@qq.com`:格式必须为邮箱格式。
- `访问地址`localhost:80