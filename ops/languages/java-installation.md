# Java Installation

## Install
- Create a java folder under usr  
``` shell
cd /usr
mkdir java
chmod 777 java
```

- Put installer package in this folder and unzip it  
```shell
tar -zxvf jdk-13_linux-x64_bin.tar.gz
```

## Environment Configuration
``` shell
vim /etc/profile
export JAVA_HOME=/usr/java/jdk-13
source /etc/profile
```

## Validation
- Check the java version
``` shell
java -version
```

- Check the gabage collection version
``` shell
java -XX:+PrintCommandLineFlags -version
```


# References
Java
https://www.oracle.com/technetwork/java/javase/downloads/index.html