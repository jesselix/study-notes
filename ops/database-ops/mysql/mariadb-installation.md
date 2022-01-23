# MariaDB Installation

## Install MariaDB
- Install
``` zsh
apt install mariadb-server
```

- Check version
``` zsh
mysql -V
```

- Other operations
``` zsh
systemctl status mariadb
systemctl start mariadb
systemctl stop mariadb
systemctl restart mariadb
```

- Login MariaDB
``` zsh
mysql -u root -p
```

## utf8 / utf8mb4 Problem
- Check for character sets
``` zsh
show variables like "%character%";show variables like "%collation%";
```

- modify character sets
``` zsh
set names utf8mb4;
```

## Create a New User
``` zsh
create user 'root'@'%' identified by 'root';
grant all privileges on *.* to 'root'@'%' with grant option;
flush privileges;
flush privileges;
```

- Set root remote permission (not recommanded)
``` zsh
grant all privileges on *.* to 'root'@'%' identified by '123456' with grant option;
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



