# MySQL-Java Types
References
MySQL 数据类型
https://www.runoob.com/mysql/mysql-data-types.html
MySQL——VARCHAR和CHAR类型
https://blog.csdn.net/weixin_42570248/article/details/89786882

http://www.piaoyi.org/database/MYSQL-INT-TIMESTAMP-DATETIME.html
https://www.jianshu.com/p/83ffccc5215e
https://www.cnblogs.com/mxwz/p/7520309.html
https://www.cnblogs.com/mxwz/p/7520309.html

Java中Long型数据类型对应MySQL数据库中哪种类型？
https://blog.csdn.net/weixin_39746740/article/details/82053908


主键索引
主键是一种唯一性索引，但它必须指定为“PRIMARY KEY”。

普通索引
普通索引是最基本的索引类型，而且它没有唯一性之类的限制。

区别
普通索引是最基本的索引类型，没有任何限制，值可以为空，仅加速查询。普通索引是可以重复的，一个表中可以有多个普通索引。
主键索引是一种特殊的唯一索引，一个表只能有一个主键，不允许有空值；索引列的所有值都只能出现一次，即必须唯一。简单来说：主键索引是加速查询 + 列值唯一（不可以有null）+ 表中只有一个。

索引无效
 1. 隐式转换导致索引失效.这一点应当引起重视.也是开发中经常会犯的错误.
 由于表的字段tu_mdn定义为varchar2(20),但在查询时把该字段作为number类型以where条件传给Oracle,这样会导致索引失效.
 错误的例子：select * from test where tu_mdn=13333333333;
 正确的例子：select * from test where tu_mdn='13333333333';
 2. 对索引列进行运算导致索引失效,我所指的对索引列进行运算包括(+，-，*，/，! 等)
 错误的例子：select * from test where id-1=9;
 正确的例子：select * from test where id=10;
 3. 使用Oracle内部函数导致索引失效.对于这样情况应当创建基于函数的索引.
 错误的例子：select * from test where round(id)=10; 说明，此时id的索引已经不起作用了
 正确的例子：首先建立函数索引，create index test_id_fbi_idx on test(round(id));然后 select * from test where round(id)=10; 这时函数索引起作用了
 4. 以下使用会使索引失效，应避免使用；
 a. 使用 <> 、not in 、not exist、!=
 b. like "%_" 百分号在前（可采用在建立索引时用reverse(columnName)这种方法处理）
 c. 单独引用复合索引里非第一位置的索引列.应总是使用索引的第一个列，如果索引是建立在多个列上, 只有在它的第一个列被where子句引用时，优化器才会选择使用该索引。
 d. 字符型字段为数字时在where条件里不添加引号.
 e. 当变量采用的是times变量，而表的字段采用的是date变量时.或相反情况。
 5. 不要将空的变量值直接与比较运算符（符号）比较。
 如果变量可能为空，应使用 IS NULL 或 IS NOT NULL 进行比较，或者使用 ISNULL 函数。
 6. 不要在 SQL 代码中使用双引号。
 因为字符常量使用单引号。如果没有必要限定对象名称，可以使用（非 ANSI SQL 标准）括号将名称括起来。
 7. 将索引所在表空间和数据所在表空间分别设于不同的磁盘chunk上，有助于提高索引查询的效率。
 8. Oracle默认使用的基于代价的SQL优化器（CBO）非常依赖于统计信息，一旦统计信息不正常，会导致数据库查询时不使用索引或使用错误的索引。
 一般来说，Oracle的自动任务里面会包含更新统计信息的语句，但如果表数据发生了比较大的变化（超过20%）,可以考虑立即手动更新统计信息，例如：analyze table abc compute statistics，但注意，更新   统计信息比较耗费系统资源，建议在系统空闲时执行。
 9. Oracle在进行一次查询时，一般对一个表只会使用一个索引.
 因此，有时候过多的索引可能导致Oracle使用错误的索引，降低查询效率。例如某表有索引1（Policyno）和索引2（classcode），如果查询条件为policyno = ‘xx’ and classcode = ‘xx’，则系统有可能会使用索   引2，相较于使用索引1，查询效率明显降低。
 10. 优先且尽可能使用分区索引。





Isolation Level


隔离级别
	脏读	不可重复读	幻读
Read uncommitted	√	√	√
Read committed	×	√	√
Repeatable read	×	×	√
Serializable	×	×	×

脏读
一个事务A读取了被另一个事务B修改，但是还未提交的数据。假如B回退，则事务A读取的是无效的数据。

不可重复读
在基于锁的并行控制方法中，如果在执行select时不添加读锁，就会发生不可重复读问题。

幻读
当两个完全相同的查询执行时，第二次查询所返回的结果集跟第一个查询不相同。

很多人容易搞混不可重复读和幻读，确实这两者有些相似。但不可重复读重点在于update（改）和delete（删），而幻读的重点在于insert（增）。


References
数据库事务隔离级别 - 分析脏读 & 不可重复读 & 幻读
https://www.cnblogs.com/balfish/p/8298296.html

不可重复读和幻读的区别
https://www.jianshu.com/p/4b6e0103a13c





SQL Tools


Explain
显示查询使用了何种类型,从最好到最差依次是:system > const > eq_ref > ref > range > index > all



sql优化工具explain的使用
https://blog.csdn.net/littlexiaoshuishui/article/details/90543894






Shard


分库分表
方案1：停机
方案2：双写


哈希分发

分库分表中间件



8种MySQL分页方法总结
https://www.imooc.com/article/47409





数据库分库分表思路
https://www.cnblogs.com/butterfly100/p/9034281.html
深入分析mysql为什么不推荐使用uuid或者雪花id作为主键
https://www.cnblogs.com/wyq178/p/12548864.html?utm_source=tuicool&utm_medium=referral