# Docker

deamon
image
container

Data Volume
容器删除后，容器里面的数据不在了。
在容器里创建一个目录，绑定宿主机的目录。宿主机的该目录就是数据卷。
一个数据卷可以被多个容器挂载。

配置
docker run … -v 宿主机目录:容器目录

数据卷容器



# References
干货满满！10分钟看懂Docker和K8S  
https://my.oschina.net/jamesview/blog/2994112

新版Docker 2020-传智播客  
https://www.bilibili.com/video/BV187411o7vR?p=10

Ubuntu安装Docker及Docker的基本命令  
https://www.jianshu.com/p/80e3fd18a17e

https://docs.docker.com/engine/install/ubuntu/
