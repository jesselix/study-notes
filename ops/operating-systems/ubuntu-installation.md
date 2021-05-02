# Ubuntu Installation

更新 -> 检查更新 apt update

## Check updates
- Check for updates
``` bash
apt update
apt upgrade
```

## Swap
- Check if any swap file exist. If the followwing command returns empty, it means swap file doesn't exist. 
``` bash
swapon -s
```

- Get into var direction
``` bash
cd /var
```

- Create a swap file
``` bash
dd if=/dev/zero of=swapfile bs=1M count=2048
```

- Turn it into swap file
``` bash
mkswap swapfile
```

- Enable this swap file
``` bash
swapon swapfile
```

- Modify permission for swap file
``` bash
chmod -R 0600 swapfile
```

- Load swap file automatically when computer starts
``` bash
echo "/var/swapfile swap swap defaults 0 0" >> /etc/fstab
```

## Firewall
防火墙 -> 端口设置 永久开放80端口 firewall-cmd --permanent --zone=public --add-port=80/tcp

永久关闭80端口 firewall-cmd --permanent --zone=public --remove-port=80/tcp

--zone #作用域 --add-port=80/tcp  #添加端口，格式为：端口/通讯协议 --permanent   #永久生效，没有此参数重启后失效

查看开放的端口号 firewall-cmd --zone=public --list-ports

查看防火墙状态 systemctl status firewalld.service

查看防火墙命令 firewall-cmd -h