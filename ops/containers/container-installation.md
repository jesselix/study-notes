# Container Installation

## MariaDB Installation
### Install
- Download MariaDB from Docker Hub.
``` bash
docker pull mariadb
```

- Check the docker image
``` bash
docker images
```

### Docker Operations
- Run the docker
``` bash
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
``` bash
docker exec -it docker-mariadb bash
```

## PostgreSQL Installation
### Install
- Download postgresSQL from Docker Hub
``` shell
docker pull postgres
```

### Validation
- Check the docker image
``` bash
docker images
```

### Run
``` bash
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
``` bash
docker exec -it docker-postgres bash
```

---
## References
> Docker安装PostgreSQL  
https://www.jianshu.com/p/75a7421cf787