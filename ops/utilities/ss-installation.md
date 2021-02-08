# SS Installation

## Installation
- Install python-pip  
go to: <u>Python Installation</u>

- Install Shadowsocks
``` bash
pip install shadowsocks
```

## Operations
- Start SS
``` bash
ssserver -c /etc/shadowsocks.json -d start
```

- Stop SS
``` bash
ssserver -c /etc/shadowsocks.json -d stop
```

---

## References
> shadowsocks  
https://github.com/shadowsocks/shadowsocks/wiki/Ports-and-Clients#windows

> 科学上网 - VPS 搭建 Shadowsocks 并开启 BBR  
https://meilbn.com/2017/10/25/VPS-build-shadowsocks-and-bbr/