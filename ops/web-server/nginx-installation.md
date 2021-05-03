# Nginx Installation

## Install Nginx
- Install
``` bash
apt install nginx
```

- Check the version
``` bash
nginx -v
```

- Check the status
``` bash
service nginx status
```

## Firewall Configuration
- Set permission for firewall
``` bash
ufw allow OpenSSH
ufw allow 'Nginx HTTP'
```

- Check firewall status
``` bash
ufw status
```

## Nginx Continue
- Check Nginx by typing ip in browser.
