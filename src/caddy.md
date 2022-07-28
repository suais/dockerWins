# **Docker安装Caddy** #
## 服务简介 ##
Caddy是一个相对年轻的简化了主机和加密的web服务器（目前公共开发了超过1年的时间）。Caddy使用Let’s Encrypt使得使用Caddy的网站可以免费获得SSL加密。它的开发相当活跃，我们也非常欢迎和鼓励外部的帮助。如果有哪些我们还没有的功能可以随时提出，而且将新功能添加进去也不会花费太长的时间。


 <img src="./../images/caddy.png" width = "420" alt="Github" align=center />

* * *

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />

[ Github ](https://github.com/caddyserver/caddy)
## 准备镜像 ##
    docker pull caddy
## 运行容器 ##
使用TLS

     docker run -d -p 80:80 -p 443:443 -v my-website:/srv  -v caddy_data:/data -v caddy-config:/config caddy caddy file-server --domain localhost
#### 参数说明 ####
- `-v my-website:/srv`：网站文件挂载目录
- `--domain localhost`：指定域名，此处为本地域名