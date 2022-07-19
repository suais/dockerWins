# Docker安装showDoc #
## 服务简介 ##
ShowDoc是一个非常适合IT团队的在线API文档、技术文档工具。通过showdoc，你可以方便地使用markdown语法来书写出美观的API文档、数据字典文档、技术文档、在线excel文档等等。如果不想编辑markdown文档，你还可以利用showdoc的自动化能力，从程序注释中自动生成API文档，或者从搭配的RunApi客户端（类似postman的api调试工具）中一边调试接口、一边自动生成文档。通过分配项目成员和团队成员，你可以很方便地进行项目文档的权限管理和团队协作，也可以分享文档出去给朋友查看。ShowDoc还支持多平台客户端，有win客户端、mac客户端、ios、android等，更方便跨平台使用。目前超过100000+的互联网团队正在使用showdoc，包括知名公司内部的一些团队，比如腾讯、华为、百度、京东、字节跳动、顺丰等等。

[ showDoc Github](https://github.com/star7th/showdoc)

## 准备镜像 ##
    docker pull star7th/showdoc
## 运行容器 ##
    docker run -d 
    --name showdoc 
    -p 80:80 
    -v /showdoc_data/html:/var/www/html/ star7th/showdoc

## 常见说明 ##
`访问地址`：localhost:80