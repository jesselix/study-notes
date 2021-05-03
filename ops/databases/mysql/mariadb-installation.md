# MariaDB Installation

## Install MariaDB
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

- Reset root password
``` bash
alter user 'root'@'localhost' IDENTIFIED VIA mysql_native_password USING password('ZzAlpha1!mr');
```

- Other operations
``` bash
systemctl status mariadb
systemctl start mariadb
systemctl stop mariadb
systemctl restart mariadb
```

## utf8 Problem
- Check for character sets
``` bash
show variables like "%character%";show variables like "%collation%";
```

- modify character sets
``` bash
set names utf8mb4;
```

## Set remote connection
- Check port 3306 status
``` bash
netstat -an | grep 3306
```

- The following return message means port 3306 only listens 127.0.0.1
``` bash
tcp        0      0 127.0.0.1:3306          0.0.0.0:*               LISTEN
```

- Let port 3306 to be listened by other IPs
``` bash
vim /etc/mysql/mariadb.conf.d/50-server.cnf
```

- Find the following message and uncomment it.
``` bash
bind-address            = 127.0.0.1
```

- The following return message means port 3306 listens all IPs
``` bash
tcp6       0      0 :::3306                 :::*                    LISTEN
```

- Add allowed port
``` bash
ufw allow 3306
```

- Set root remote permission (not recommanded)
``` bash
grant all privileges on *.* to 'root'@'%' identified by '123456' with grant option;
flush privileges;
```

- Create a new user
``` bash
grant all on *.* to someone@'%' identified by '123456' with grant option;
flush privileges;
```