# **Docker安装Vault** #
## 服务简介 ##

<img src="./../images/ault.png" width = "420" alt="Github" align=center />

* * *

ashiCorp Vault 的 Slogan 是 A Tool for Managing Secrets，这个口号很好的描述了该产品的定位。大多数软件项目都会不同程度的用到诸如 登录密码/Token/证书/API Key 等私密信息，这些信息用明码保存显然是很不安全的，如果不小心签入到版本控制系统，还会造成重大的安全问题（这方面的事故我们已经听到过很多次了）。

Vault 就是为了解决这一问题而创立的。它提供了这些功能：

- 集中管理各种私密信息；
- 为私密信息设置租期（Lease），到期后自动失效；
- 密钥的动态生成、注销和滚动更新；
- 动态创建无需保存的一次性登录密钥；
- 作为数据加密/解密接口；
- 完整的审计记录；
- 命令行 以及 RESTful API 访问接口；
此外，Vault 设计为灵活的可插拔架构，允许灵活的设置各种后端引擎和安全策略。例如：

- 可以用内置 Token、用户/密码、LDAP、Amazon IAM、Github 等作为认证授权机制；
- 可以使用内存/本地文件/Etcd/Consul/ZooKeeper/RDBMS/NoSQL/云平台等作为数据存储；
- 可以为数据库/SSH/Consul/AWS/Nomad/PKI/RabbitMQ 等多种平台生成和管理访问密钥；
- 可以与 Cousul、Chef、Ansible 等运维工具集成起来共同使用；


 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />
 
[ GitHub ](https://github.com/hashicorp/vault)
## 准备镜像 ##
    docker pull vault
## 运行容器 ##
#### 参数说明 ####