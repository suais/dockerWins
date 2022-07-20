# Docker安装prometheus #
## 服务简介 ##

<img src="./../images/prometheus.png" width = "420" alt="Github" align=center />

* * *

Prometheus(中文名:普罗米修斯)是由SoundCloud开发的开源监控报警系统和时序列数据库(TSDB)。Prometheus使用Go语言开发, 是Google BorgMon监控系统的开源版本。

Prometheus的基本原理是通过HTTP协议周期性抓取被监控组件的状态，任意组件只要提供对应的HTTP接口就可以接入监控，不需要任何SDK或者其他的集成过程。输出被监控组件信息的HTTP接口被叫做exporter，目前开发常用的组件大部分都有exporter可以直接使用，比如Nginx、MySQL、Linux系统信息、Mongo、ES等。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />

[prometheus GitHub](https://github.com/prometheus/prometheus)

## 准备镜像 ##
    docker pull prom/prometheus
## 运行容器 ##
    docker run -d 
    -p 9090:9090 
    -v opt/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml 
    --name prometheus prom/prometheus
## 常见说明 ##
首先需要在`/opt/prometheus`目录下添加配置文件prometheus.yml：

    global:  
        scrape_interval:   60s  
        evaluation_interval: 60s 
    scrape_configs:
        - job_name: prometheus
            static_configs:
              - targets: ['localhost:9090']
                labels:
                    instance: prometheus


- `访问graph页面`:http://IP:9090/graph
- `访问targets页面`: http://IP:9090/targets

exporter安装可参见：[Docker安装exporte](./exporter.md)