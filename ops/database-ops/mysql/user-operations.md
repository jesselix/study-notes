# User Operations

## Login
- Login by user1
``` zsh
mysql -u user1 -p
```

``` zsh
mysql -u root -p
```

## User Creation
- Create a user 'user1'
``` zsh
create user 'user1'@'%' identified by 'www';

grant all on *.* to 'user1'@'%';
```

## User Deletion
- Delete user 'user1'
``` sql
delete from mysql where user = 'user1'
```


## Password
``` zsh
SET password for 'user1'@'localhost'=password('newpassword');
SET password for 'user1'@'%'=password('newpassword');
```

## Authorization
``` zsh
grant all on *.* to 'jesselix'@'%';
```

# References
docker安装postgresql  
https://www.cnblogs.com/SmilingEye/p/11835040.html

https://www.jianshu.com/p/80e3fd18a17e
https://blog.sunriseydy.top/technology/server-blog/server/docker_install_mysql/
https://www.cnblogs.com/edisonchou/p/docker_volumes_introduction.html