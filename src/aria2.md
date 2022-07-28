# **Docker安装Aria2** #
## 服务简介 ##

 <img src="./../images/OIP-C.jpg" width = "420" alt="Github" align=center />

* * *

本安装用到2个镜像容器，分别是Aria2和Ariang，Aria2提供下载服务，而Ariang提供了一个web端服务的ui管理界面。

免费轻量级命令行下载工具:Aria2
Aria2是一款开源下载工具，可帮助简化不同设备和服务器之间的下载过程。它支持磁力链接、BT种子、http等类型的文件下载，与迅雷及QQ旋风相比，Aria2有着优秀的性能及较低的资源占用,架构本身非常轻巧，通常只需要4兆字节（HTTP下载）到9兆字节（用于BitTorrent交互）之间。最重要的一点是Aria2完全免费！

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />

[aria2 Github](https://github.com/aria2/aria2)

## 准备镜像 ##
准备Aria2镜像，在CMD(Windows)或Terminal(Linux、Mac)输入以下命令：

    docker pull p3terx/aria2-pro

准备Ariang镜像，在CMD(Windows)或Terminal(Linux、Mac)输入以下命令：

    docker pull p3terx/ariang

## 运行容器 ##

运行Aria2-pro容器，在CMD(Windows)或Terminal(Linux、Mac)输入以下命令：

    docker run -d \
     --name aria2-pro \
     --restart always \
     --log-opt max-size=1m \
     -e PUID=$UID \
     -e PGID=$GID \
     -e UMASK_SET=022 \
     -e RPC_SECRET=password \
     -e RPC_PORT=6800 \
     -p 6800:6800 \
     -e LISTEN_PORT=6888 \
     -p 6888:6888 \
     -p 6888:6888/udp \
     -v /docker_volume/name/config:/config \
     -v /docker_volume/name/downloads:/downloads \
     p3terx/aria2-pro \

#### 参数说明 ####

- `-e RPC_SECRET=password`:此环境变量为ariang需要填写的链接密钥，可自行更改
- `-e RPC_PORT=6800`:此环境变量为ariang需要填写的链接端口，需要与宿主机暴露的端口一致
- -v 挂在目录需根据实际需要进行更改，如果经常下载一些大文件，请将downloads目录挂载到较大空间，或者挂载至远程下载盘上

运行Ariang容器，在CMD(Windows)或Terminal(Linux、Mac)输入以下命令：

    docker run -d \
    --name ariang \
    --log-opt max-size=1m \
    --restart unless-stopped \
    -p 6880:6880 \
    p3terx/ariang

## 常见说明 ##
运行成功后，在常用的浏览器中访问：`localhost:6880`，进入Ariang配置页面，Ariang设置页面，点击`Ariang设置`，输入RPC相关信息，地址填写为宿主机IP地址，RPC密钥填写为创建`Aria2-pro`容器时填入的`RPC_SECRET`。