# Container Installation

## MySQL Installation
### Install
- Download MariaDB from Docker Hub
``` zsh
docker pull mysql
docker pull mariadb
docker pull postgres
```

### Validation
- Check the docker image
``` zsh
docker images
```

### Docker Operations for MySQL
- Edit the my.cnf file

- Run the docker
``` zsh
docker run --restart=always --privileged=true \
-p 3306:3306 --name docker-mysql \
-v /var/docker/mysql/logs:/var/log/mysql \
-v /var/docker/mysql/data:/var/lib/mysql \
-v /var/docker/mysql/conf:/etc/mysql \
-v /var/docker/mysql/mysql-files:/var/lib/mysql-files/ \
-e TZ=Asia/Shanghai \
-e MYSQL_ROOT_PASSWORD='root123' \
-d mysql:latest
```

- Get into MySQL container
``` zsh
docker exec -it docker-mysql bash
```

- Check full container id
``` zsh
docker ps --no-trunc
```

---
## References
> 使用Docker搭建MySQL服务  
https://www.cnblogs.com/sablier/p/11605606.html
