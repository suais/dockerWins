# Docker安装gogs #
## 服务简介 ##

 <img src="./../images/gogos.jpg" width = "420" alt="Github" align=center />

* * *

Gogs 是一款极易搭建的自助 Git 服务，打造一个以最简便的方式搭建简单、稳定和可扩展的自助 Git 服务。使用 Go 语言开发使得 Gogs 能够通过独立的二进制分发，并且支持 Go 语言支持的 所有平台，包括 Linux、macOS、Windows 和基于 ARM 的操作系统。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />

[gogs Github](https://github.com/gogs/gogs)

## 准备镜像 ##
    docker pull pull gogs/gogs
## 运行容器 ##
    docker run -p 10022:22 
    -p 10080:3000 --name=gogs \
    -v /mydata/gogs:/data  \
    -d gogs/gogs
## 常见说明 ##
- 10022对应的是Gogs的SSH服务端口，10080对应的使用Gogs的HTTP服务端口，我们还将容器的数据目录挂载到了宿主机的/mydata/gogs目录下，这样就算我们重新创建容器数据也不会丢失
- 安装完成后，我们第一次访问Gogs服务会显示一个设置页面
- 数据库设置，这里我们直接使用内置的SQLite3数据库即可，使用其他的需要自行搭建数据库
- 应用基本设置，主要修改域名、SSH端口号和应用URL即可：SSH端口配置为：10022
- 在局域网内使用gogs，可以将域名配置为宿主机的IP地址
- 注册完成后会直接跳转到登录界面，首先需要注册一个账号
- `访问地址`：localhost:10080