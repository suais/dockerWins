# **Docker安装Api-firewall** #
## 服务简介 ##

 <img src="./../images/Wallarm_Logo.png" width = "420" alt="Github" align=center />

* * *
 
 API Firewall是一个高性能代理，具有基于OpenAPI/Swagger模式的API请求和响应验证。它被设计用来保护云原生环境中的REST API端点。API Firewall通过使用积极的安全模型提供API加固，允许符合预定义API规范的请求和响应的调用，同时拒绝其他一切不符合要求的连接。

主要特点是:
- 通过阻止恶意请求来确保REST API端点的安全
- 通过阻断畸形的API响应来阻止API数据的泄露
- 为基于OAuth 2.0协议的认证验证JWT访问令牌
- (新) 拒绝被泄露的API令牌、密钥和Cookies

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />

[ Github ](https://github.com/wallarm/api-firewall)
## 准备docker-compose ##
    git clone https://github.com/wallarm/api-firewall.git
## 运行容器 ##
    cd api-firewall/demo/docker-compose
    make start
#### 参数说明 ####
检查API防火墙是否阻止发送到未暴露路径的请求:
    curl -sD - http://localhost:8080/unexposed/path