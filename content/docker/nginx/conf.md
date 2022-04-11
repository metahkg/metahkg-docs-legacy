---
title: Nginx Configuration
pcx-content-type: concept
weight: 3
layout: list
meta:
  title: Nginx Configuration
---

# Nginx configuration

Assuming you use:

- port 3001 for api
- port 3002 for web app

## Configuration file

Create a nginx configuration file:

```bash
sudo nano /etc/nginx/sites-available/example.com.conf
# it is recommended to use your domain name for the configuration file name (with .conf)
```

## Self signed certificate, or you already have a certificate

```nginx
# /etc/nginx/sites-available/example.com.conf

server {
    server_name example.com;
    # replace example.com with your domain

    server_tokens off;

    listen 443 ssl;
    listen [::]:443 ssl;

    ssl_certificate /etc/ssl/certs/ssl-cert-snakeoil.pem;
    # replace with your certificate
    ssl_certificate_key /etc/ssl/private/ssl-cert-snakeoil.key;
    # replace with your private key

    location /api {
        proxy_pass http://localhost:3001;
    }
    location / {
        proxy_pass http://localhost:3002;
    }
}
server {
    server_name example.com;
    # replace with your domain

    server_tokens off;

    listen 80;
    listen [::]:80;

    return 301 https://$host$request_uri;
}
```

## Use Let's encrypt for certificate

```nginx
# /etc/nginx/sites-available/example.com.conf

server {
    server_name example.com;
    # replace example.com with your domain

    server_tokens off;

    listen 80;
    listen [::]:80;

    location /api {
        proxy_pass http://localhost:3001;
    }
    location / {
        proxy_pass http://localhost:3002;
    }
}
```

## Enable the site

```bash
$ ln -s /etc/nginx/sites-available/example.com.conf /etc/nginx/sites-enabled/
# replace the filename with yours

$ sudo systemctl reload nginx
# reload nginx
```

Metahkg is now available at your domain.
If you use [let's encrypt](https://letsencrypt.org), follow the steps at [letsencrypt](../letsencrypt).
