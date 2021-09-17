# Ubuntu Installation

## Check updates
- Check for updates
``` zsh
apt update
apt upgrade
```

## Swap file
- Check if any swap file exist. If the followwing command returns empty, it means it doesn't exist. 
``` zsh
swapon -s
```

- Get into var direction
``` zsh
cd /var
```

- Create a file
``` zsh
dd if=/dev/zero of=swapfile bs=1M count=2048
```

- Turn it into swap file
``` zsh
mkswap swapfile
```

- Enable this swap file
``` zsh
swapon swapfile
```

- Modify permission for swap file
``` zsh
chmod -R 0600 swapfile
```

- Load swap file automatically when computer starts
``` zsh
echo "/var/swapfile swap swap defaults 0 0" >> /etc/fstab
```

## Firewall
- Check firewall status
``` zsh
ufw status
```

- Enable firewall
``` zsh
ufw enable
```

- Add allowed port
``` zsh
ufw allow 22
```