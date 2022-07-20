# Docker安装calibre-web #
## 服务简介 ##
 <img src="./../images/calibre-web.png" width = "420" alt="Github" align=center />

* * *
Calibre是电子书管理解决方案，本地版使用了很多年，发现可以突破本地服务的局限，为自己的各种终端提供电子书服务。

Calibre-web就是calibre的web版，它提供了用户友好的对外网页展示的形式，可以在网上展示，管理，浏览自己的书籍，让书跟着自己走。


 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />

[calibre-web Github](https://github.com/janeczku/calibre-web)

## 准备镜像 ##
    docker pull technosoft2000/calibre-web

## 运行容器 ##

    sudo docker run -d \
    --name=calibre-techno-web \
    -e TZ=Asian/Shanghai \
    -e DOCKER_MODS=linuxserver/calibre-web:calibre \
    -p 8083:8083 \
    -v /docker_volume/calibre-web/config:/config \
    -v /docker_volume/calibre-web/books:/books \
    --restart unless-stopped \
    technosoft2000/calibre-web

## 常见说明 ##
`初始化`:安装容器成功后，需要打开本地的calibre客户端，点击Calibre Library，找到您客户端中library存储的位置，复制medadata.db数据库文件至您映射的books目录下。

初始化成功后的账号是：admin，
密码是：admin123，通过浏览器打开locaohost:8083即可访问。