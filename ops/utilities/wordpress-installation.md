# WordPress Installation

This WordPress Installation is based on LEMP(Linux, Nginx, MariaDB and PHP) environment. The website xxx.com is going to be installed.

##  Install Nginx  
- Go to: <u>Nginx Installation</u>

## Install MariaDB  
- Go to: <u>MariaDB Installation</u>

- Create a database (e.g. xxx_com) for the WordPress website.

## Install PHP  
- Go to: <u>PHP Installation</u>

## Install WordPress  
- Create the xxx.com folder for the website under /var/www/html.

- Download WordPress package from official website and unzip it to the website folder.

## Nginx Configuration
- Create and edit the configuration file (e.g. xxx_com) under /etc/nginx/sites-available.

- Create a link under /etc/nginx/sites-enabled.
``` bash
ln -s /etc/nginx/sites-available/xxx-com /etc/nginx/sites-enabled/xxx-com
```

## WordPress Configuration
- Type in xxx.com from browser and go to the website.

- Follow the instruction and go ahead for the database. Database configuration can be edited in wp-config.php.
