# Nginx Installation

## Install Nginx
- Ubuntu
``` shell
apt install nginx
```

- Check the version
``` shell
nginx -v
```

- Check the status
``` shell
service nginx status
```

## Firewall Configuration
- Set permission for firewall
``` shell
ufw allow OpenSSH
ufw allow 'Nginx HTTP'
```

- Check firewall status
``` shell
ufw status
```

## Nginx Continue
- Check Nginx by typing ip in browser.
