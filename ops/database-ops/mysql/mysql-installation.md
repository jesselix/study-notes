# MySQL Installation

## Install MySQL
- Install
``` zsh
apt install mysql-server
```

- Check version
``` zsh
mysql -V
```

- Other operations
``` zsh
systemctl status mysql
systemctl start mysql
systemctl stop mysql
systemctl restart mysql
```

- Setup
``` zsh
mysql_secure_installation
```

- Login MySQL
``` zsh
mysql -u root -p
```

## utf8 / utf8mb4 Problem
- Check for character sets
``` zsh
show variables like "%character%";show variables like "%collation%";
```

- modify my.cnf
``` zsh
vim /etc/mysql/my.cnf
```

- insert the following contents
``` zsh
[client]
default-character-set = utf8mb4

[mysql]
default-character-set = utf8mb4

[mysqld]
character-set-client-handshake = FALSE
character-set-server = utf8mb4
collation-server = utf8mb4_unicode_ci
init_connect='SET NAMES utf8mb4'
```

## Create a New User
``` zsh
create user 'jesselix'@'%' identified by 'www';
grant all privileges on *.* to 'jesselix'@'%' with grant option;
flush privileges;
```

- Set root remote permission (not recommanded)
``` zsh
create user 'root'@'%' identified by 'root';
grant all privileges on *.* to 'root'@'%' with grant option;
flush privileges;
```

## Set remote connection
- Check port 3306 status
``` zsh
netstat -an | grep 3306
```

- The following return message means port 3306 only listens 127.0.0.1
``` zsh
tcp        0      0 127.0.0.1:3306          0.0.0.0:*               LISTEN
```

- Let port 3306 to be listened by other IPs
``` zsh
vim /etc/mysql/mariadb.conf.d/50-server.cnf
```

- Find the following message and uncomment it.
``` zsh
bind-address            = 127.0.0.1
```

- The following return message means port 3306 listens all IPs
``` zsh
tcp6       0      0 :::3306                 :::*                    LISTEN
```

- Add allowed port
``` zsh
ufw allow 3306
```

## References
更改MySQL数据库的编码为utf8mb4  
https://blog.csdn.net/woslx/article/details/49685111
