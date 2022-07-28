# **Docker安装Gradle** #
## 服务简介 ##

 <img src="./../images/gradle.jpg" width = "420" alt="Github" align=center />

* * *
Gradle是一个专注于构建自动化和支持多语言开发的构建工具。如果你在任何平台上构建、测试、发布和部署软件，Gradle提供了一个灵活的模型，可以支持从编译和打包代码到发布网站的整个开发生命周期。Gradle被设计为支持跨语言和平台的构建自动化，包括Java、Scala、Android、C/C++和Groovy，并与开发工具和持续集成服务器紧密集成，包括Eclipse、IntelliJ和Jenkins。

 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />
 
[ Github ](https://github.com/gradle/gradle)
## 准备镜像 ##
    docker pull gradle
## 运行容器 ##
从你要构建的Gradle项目的目录中运行:

    docker run --rm -u gradle -v "$PWD":/home/gradle/project -w /home/gradle/project gradle gradle <gradle-task>
    
#### 参数说明 ####
- 注意上述命令使用uid/gid 1000（用户gradle）运行，以避免以root身份运行
- 如果你正在挂载一个卷，而运行Docker的uid/gid不是1000，你应该以用户root的身份运行（-u root）。root也是默认的，所以你也可以直接不指定用户。