# Java Installation

## Install
- Create a java folder under usr  
``` bash
cd /usr
mkdir java
chmod 777 java
```

- Put installer package in this folder and unzip it  
```bash
tar -zxvf jdk-13_linux-x64_bin.tar.gz
```

## Environment Configuration
``` zsh
vim /etc/profile
export JAVA_HOME=/usr/java/jdk-13
source /etc/profile
```

## Validation
- Check the java version
``` zsh
java -version
```

- Check the gabage collection version
``` bash
java -XX:+PrintCommandLineFlags -version
```


# References
Java
https://www.oracle.com/technetwork/java/javase/downloads/index.html