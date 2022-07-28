# **Docker安装Rethinkdb** #
## 服务简介 ##

<img src="./../images/rethinkdb.png" width = "420" alt="Github" align=center />

* * *
RethinkDB最早是作为一个对SSD进行专门优化的MySQL存储引擎出现的，其特点在于对SSD的充分利用。而目前RethinkDB已经脱离MySQL成为一个独立的存储。

它可以用来替代Memcached作为数据缓存层。或者替代一些类似Memcached的存储，比如Membase，MemcacheDB，TokyoTyrant及Schooner Membrain等。RethinkDB为各种应用压力下提供高性能和高可靠性 支持，主要应用在下面一些场景：

    (adsbygoogle = window.adsbygoogle || []).push({}); 

- 用来处理一些其它方案无法解决的服务负载（如：要求快速的服务启动，在数据量超出内存大小后还要有高的性能，处理各种不稳定的读写压力，处理大量数据等）
- 提供性能与数据稳定性之间的精细调控
- 大大提高你的缓存层和key-value存储的性能，在你现有的硬件条件下，能支持更高的应用负载。


 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />
 
[ GitHub ](https://github.com/rethinkdb/rethinkdb)
## 准备镜像 ##
## 运行容器 ##
#### 参数说明 ####