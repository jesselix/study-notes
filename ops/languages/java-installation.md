# Java Installation

## Install

- Update softwares list
``` bash
apt update
```

- Install OpenJDK
```bash
apt install openjdk-17-jdk
```

## Environment Configuration

- Edit .bashrc
``` bash
vim ~/.bashrc
```

- Add the following lines
``` bash
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
export PATH=$JAVA_HOME/bin:$PATH
```

## Validation

- Check the java version
``` bash
java -version
```

- Check the gabage collection version
``` bash
java -XX:+PrintCommandLineFlags -version
```


# References
Java
https://www.oracle.com/technetwork/java/javase/downloads/index.html