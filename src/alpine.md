# **Docker安装Alpine Linux** #
## 简介 ##

 <img src="./../images/alpinelinux-logo.svg" width = "420" alt="Github" align=center />

* * *

Alpine Linux是针对安全目标的轻量级Linux发行版，基于musl libc和Busybox。

最初 Alpine Linux 起源于 LEAF (Linux Embedded Applicance Framework)项目，而 LEAF 项目则又是从一个非常小巧的 Linux Router Project(LRP)项目fork出来的。由此可见，Alpine从一开始其核心理念就是创建一个轻量级、精简的并且运行在内存中的防火墙/代理服务器/VPN专用发行版。

Alpine以其小巧、简单在docker容器中得到了广泛的应用。但是Alpine Linux使用了musl，可能和其他Linux发行版使用的glibc实现会有些不同。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />

[ Github ](https://github.com/alpinejs/alpine)
## 准备镜像 ##
    docker pull alpine
## 运行容器 ##
    docker run -dit --name alpine alpine
#### 参数说明 ####