# MariaDB Installation

## Install Nginx
- Install
``` bash
install mariadb-server
```

- Check version
``` bash
mysql -V
```

- Login MariaDB
``` bash
mysql -u root -p
```

- Other operations
``` bash
systemctl status mysql
systemctl restart mysql
systemctl start mysql
systemctl stop mysql
```

- Reset root password
``` bash

```

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