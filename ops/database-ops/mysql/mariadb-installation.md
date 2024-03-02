# MariaDB Installation

## Install MariaDB
- Install
``` bash
apt install mariadb-server
```

- Check version
``` bash
mysql -V
```

- Other operations
``` bash
systemctl status mariadb
systemctl start mariadb
systemctl stop mariadb
systemctl restart mariadb
```

- Login MariaDB
``` bash
mysql -u root -p
```

## utf8 / utf8mb4 Problem
- Check for character sets
``` bash
show variables like "%character%";show variables like "%collation%";
```

- modify character sets
``` bash
set names utf8mb4;
```

## Modify root's Password
``` bash
alter user 'root'@'localhost' identified by 'password_123';
flush privileges;
```

## Create a New User
``` bash
create user 'jesselix'@'%' identified by 'password_123';
grant all privileges on *.* to 'jesselix'@'%' with grant option;
flush privileges;
```

- Set root remote permission (not recommanded)
``` bash
grant all privileges on *.* to 'root'@'%' identified by 'password_123' with grant option;
flush privileges;
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



