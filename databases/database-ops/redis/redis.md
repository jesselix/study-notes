# Basics


String
Hash
List
Set
Zset



RDB
RDB持久化是指在指定的时间间隔内将内存中的数据集快照写入磁盘，实际操作过程是fork一个子进程，先将数据集写入临时文件，写入成功后，再替换之前的文件，用二进制压缩存储。

优点：高可用

AOF
AOF持久化以日志的形式记录服务器所处理的每一个写、删除操作，查询操作不会记录，以文本的方式记录，可以打开文件看到详细的操作记录。

优点：一致性


References
https://blog.csdn.net/qq_34190023/article/details/82715705

redis持久化的几种方式
https://www.cnblogs.com/chenliangcl/p/7240350.html

Redis一致性
https://www.cnblogs.com/cxxjohnson/p/8519616.html

Redis单线程
https://www.bilibili.com/video/av50514461/?p=4



缓存穿透


布隆过滤器
检索一个元素是否在集合中
放id
提高判断准确率：扩大数组、增加函数
缺点：没办法把不用的值删除



References
关于缓存穿透以及简单的处理方式
https://www.jianshu.com/p/400dd82389b4?from=groupmessage




Cache Aside Pattern
读时，先读缓存，缓存没有就读数据库，把数据放入缓存，返回响应
更新时，先删缓存，再更新数据库


https://www.cnblogs.com/syyong/p/6231326.html

Redis采用的是基于内存的采用的是单进程单线程模型的KV数据库，由C语言编写。官方提供的数据是可以达到100000+的qps。

Redis快的主要原因是：
完全基于内存
数据结构简单，对数据操作也简单
使用多路 I/O 复用模型

单进程单线程好处
代码更清晰，处理逻辑更简单
不用去考虑各种锁的问题，不存在加锁释放锁操作，没有因为可能出现死锁而导致的性能消耗
不存在多进程或者多线程导致的切换而消耗CPU
单进程单线程弊端
无法发挥多核CPU性能，不过可以通过在单机开多个Redis实例来完善；
其他一些优秀的开源软件采用的模型
多进程单线程模型：Nginx
单进程多线程模型：Memcached