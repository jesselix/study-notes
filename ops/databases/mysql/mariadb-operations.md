# MariaDB Operations

-->
-> 安装
apt -y install mariadb-server mariadb-client

-> 检查版本
mysql -V

mysql -u root -p

相关命令
systemctl restart mysql #重启
systemctl start mysql #启动
systemctl stop mysql #关闭
systemctl status mysql #检查状态

utf8问题
/etc/mysql/my.cnf
[mysqld] 标签下加上：
init_connect='SET collation_connection = utf8_unicode_ci'
init_connect='SET NAMES utf8'
character-set-server=utf8
collation-server=utf8_unicode_ci
skip-character-set-client-handshake

/etc/mysql/mariadb.cnf
把utf8注释的字段的注释去掉。

重启mariadb

登陆MariaDB验证字符集
mysql> show variables like "%character%";show variables like "%collation%";


https://www.cnblogs.com/shenwenkai/p/10740266.html