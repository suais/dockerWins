# Docker安装思源笔记 #
## 服务简介 ##
思源笔记是一款本地优先的个人知识管理系统， 支持细粒度块级引用和 Markdown 所见即所得。类似于Notion。

[ siyuan Github](https://github.com/siyuan-note/siyuan)

## 准备镜像 ##
    docker pull b3log/siyua
## 运行容器 ##
    docker run \
    --name=siyuan
    -v /siyuan:/siyuan \
    -p 6806:6806 \
    -u 1000:1000 \
    b3log/siyuan \
    -resident \
    -workspace /siyuan/ \
    -accessAuthCode password
## 常见说明 ##
- `-accessAuthCode password`: 登录密码
- `访问地址`：localhost:6806