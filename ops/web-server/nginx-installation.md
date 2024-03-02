# Nginx Installation

## Delete apache2
- Check if apache2 exists or not. Apache2 takes the port 80 by default. You can either delete apache2 or change the port for nginx.
``` bash
apt autoremove apache2
```

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

- Common used locations
``` bash
cd /etc/nginx/sites-available
cd /etc/nginx/sites-enabled
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

## Nginx Browser Check
- Check Nginx by typing ip in browser. If it shows "Welcome to nginx!", it means it's successful.


