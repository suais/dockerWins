# Docker安装mrdoc #
## 服务简介 ##
MrDoc(觅思文档)是基于Python开发的在线文档系统。

MrDoc 适合作为个人和中小型团队的私有云文档、云笔记和知识管理工具，致力于成为优秀的私有化在线文档部署方案。

你可以简单粗暴地将 MrDoc 视为「可私有部署的语雀」和「可在线编辑文档的GitBook。

[mrdoc Gitee](https://gitee.com/zmister/MrDoc)
## 准备镜像 ##
    docker pull jonnyan404/mrdoc-alpine
## 运行容器 ##
    docker run -d \
    --name mrdoc \
    -p 10086:10086 \
    -v /docker_vloume/mrdoc:/app/MrDoc/config \
    -v /docker_vloume/mrdoc:/app/MrDoc/media \
    jonnyan404/mrdoc-alpine
## 常见说明 ##
- `访问地址`: localhost:10086