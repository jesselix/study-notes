# Container Installation

## MySQL/MariaDB/PostgreSQL Installation
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
- Run the docker
``` zsh
docker run -p 3306:3306 --name docker-mysql \
--restart=always \
-v /var/docker/mysql/conf:/etc/mysql \
-v /var/docker/mysql/logs:/var/log/mysql \
-v /var/docker/mysql/data:/var/lib/mysql \
-e TZ=Asia/Shanghai \
-e MYSQL_ROOT_PASSWORD='root123' \
-d mysql:latest
```

- Get into MySQL container
``` zsh
docker exec -it docker-mysql bash
```

### Docker Operations for MariaDB
- Run the docker
``` zsh
docker run \
-d \
--name docker-mariadb \
--restart=always \
-v /opt/docker/mariadb/data:/var/lib/mysql \
-v /opt/docker/mariadb/conf:/etc/mysql/conf.d \
-e MYSQL_ROOT_PASSWORD='root' \
-p 3306:3306 \
mariadb:latest
```
- Get into MariaDB container.
``` zsh
docker exec -it docker-mariadb bash
```

### Docker Operations for PostgreSQL
- Run the docker
``` zsh
docker run \
-d \
--name=docker-postgres \
--restart=always \
-v /opt/docker/postgresql/data:/var/lib/postgresql/data \
-e POSTGRES_PASSWORD='root' \
-e TZ=PRC \
-p 5432:5432 \
postgres:latest
```

- Get into PostgreSQL container.
``` zsh
docker exec -it docker-postgres bash
```

---
## References
> 使用Docker搭建MySQL服务  
https://www.cnblogs.com/sablier/p/11605606.html
