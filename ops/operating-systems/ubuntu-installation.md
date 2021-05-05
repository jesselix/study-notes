# Ubuntu Installation

## Check updates
- Check for updates
``` bash
apt update
apt upgrade
```

## Swap file
- Check if any swap file exist. If the followwing command returns empty, it means it doesn't exist. 
``` bash
swapon -s
```

- Get into var direction
``` bash
cd /var
```

- Create a file
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
- Check firewall status
``` bash
ufw status
```

- Enable firewall
``` bash
ufw enable
```

- Add allowed port
``` bash
ufw allow 22
```