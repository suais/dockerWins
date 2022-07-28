# **Docker安装Haproxy** #
## 服务简介 ##

 <img src="./../images/haproxy.png" width = "420" alt="Github" align=center />

* * *

HAProxy提供高可用性、负载均衡以及基于TCP和HTTP应用的代理，支持虚拟主机，它是免费、快速并且可靠的一种解决方案。HAProxy特别适用于那些负载特大的web站点，这些站点通常又需要会话保持或七层处理。HAProxy运行在当前的硬件上，完全可以支持数以万计的并发连接。并且它的运行模式使得它可以很简单安全的整合进您当前的架构中， 同时可以保护你的web服务器不被暴露到网络上。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />
 
[ Github ](https://github.com/haproxy/haproxy)
## 准备镜像 ##
    docker pull haproxy
## 运行容器 ##
配置目录

    mkdir /docker/haproxy-master/
    touch /docker/haproxy-master/haproxy.cfg

配置haproxy.cfg文件

    defaults
        mode            tcp
        log             global
        option          tcplog
        option          dontlognull
        option http-server-close
        option          redispatch
        retries         3
        timeout http-request 10s
        timeout queue   1m
        timeout connect 10s
        timeout client  1m
        timeout server  1m
        timeout http-keep-alive 10s
        timeout check   10s
        maxconn         3000
    frontend    mysql
        bind        0.0.0.0:13307
        mode        tcp
        log         global
        default_backend mysql_server
    
    backend     mysql_server
        balance roundrobin
        server mysql1 192.168.228.131:3307 check inter 5s rise 2 fall 3
        server mysql2 192.168.228.131:3308 check inter 5s rise 2 fall 3
    
    listen stats
        mode    http
        bind    0.0.0.0:1080
        stats   enable
        stats   hide-version
        stats uri /haproxyamdin?stats
        stats realm Haproxy\ Statistics
        stats auth admin:admin
        stats admin if TRUE

构建容器

    docker run -p 1080:1080 -p 13307:13307 -d --name haproxy-master -v /docker/haproxy-master/haproxy.cfg:/usr/local/etc/haproxy/haproxy.cfg --privileged=true haproxy

#### 参数说明 ####
