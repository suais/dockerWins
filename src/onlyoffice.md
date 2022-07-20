# Docker安装onlyoffice #
## 服务简介 ##

<img src="./../images/onlyoffice.jpg" width = "420" alt="Github" align=center />

* * *

ONLYOFFICE是将Word 、Excel、PPT 3大办公套件搬到了云端，只需要一个浏览器即可以在线使用Offic 的各种功能，主要用于团队协作，另外，ONLYOFFICE可以集成到NextCloud中。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />
 
[onlyoffice GitHub](https://github.com/ONLYOFFICE/onlyoffice-owncloud)

## 准备镜像 ##
    docker pull onlyoffice/documentserver
## 运行容器 ##
    docker run -i -t -d -p 80:80 \
    --restart=always \
    -v /docker_vloume/onlyoffice/logs:/var/log/onlyoffice \
    -v /docker_vloume/onlyoffice/data:/var/www/onlyoffice/Data \
    -v /docker_vloume/onlyoffice/lib:/var/lib/onlyoffice \
    -v /docker_vloume/onlyoffice/db:/var/lib/postgresql  
    --name onlyoffice 
    --restart="always" onlyoffice/documentserver
## 常见说明 ##
- `访问地址`:localhost:80
- `其他注意事项`:集成在nextcloud中需要配置SSL，否则无法连接