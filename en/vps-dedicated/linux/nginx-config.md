---
description: "Host a PHP website or proxy an application behind Nginx with a free SSL certificate."
icon: globe
---

# Nginx configuration

This guide creates an Nginx configuration for a website or a port proxy and puts it online with a free SSL certificate from Let's Encrypt.

{% hint style="warning" %}
If your website uses PHP, [install PHP](php-install.md) first. A pure HTML site does not need it.
{% endhint %}

{% stepper %}
{% step %}
### Install Nginx and Certbot

```bash
apt update && apt upgrade -y && apt install -y nginx certbot
```
{% endstep %}

{% step %}
### Create a new Nginx configuration

```bash
nano /etc/nginx/sites-available/<configname>.conf
```

Replace `<configname>` with the name of your site, or any name you like.
{% endstep %}

{% step %}
### Paste the configuration you need

Right-click to paste one of the configurations below, depending on your case.

{% tabs %}
{% tab title="PHP website" %}
{% code title="nginx-php-web.conf" lineNumbers="true" %}
```nginx
server_tokens off;

server {
    listen 80;
    listen [::]:80;
    server_name exemplu.dns;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;
    listen [::]:443 ssl http2;
    server_name exemplu.dns;

    root /var/www/path_site;
    index index.php;

    # allow larger file uploads and longer script runtimes
    client_max_body_size 100m;
    client_body_timeout 120s;

    sendfile off;

    # SSL configuration - replace exemplu.dns with your domain
    ssl_certificate /etc/letsencrypt/live/exemplu.dns/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/exemplu.dns/privkey.pem;
    ssl_session_cache shared:SSL:10m;
    ssl_protocols TLSv1.2 TLSv1.3;
    ssl_ciphers "ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384";
    ssl_prefer_server_ciphers on;

    # See https://hstspreload.org/ before uncommenting the line below.
    # add_header Strict-Transport-Security "max-age=15768000; preload;";
    add_header X-Content-Type-Options nosniff;
    add_header X-XSS-Protection "1; mode=block";
    add_header X-Robots-Tag none;
    add_header Content-Security-Policy "frame-ancestors 'self'";
    add_header X-Frame-Options DENY;
    add_header Referrer-Policy same-origin;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location ~ \.php$ {
        fastcgi_split_path_info ^(.+\.php)(/.+)$;
        fastcgi_pass unix:/run/php/php8.1-fpm.sock; # Change to the PHP version you have installed (e.g. 7.4, 8.0, 8.1, 8.2, 8.3)
        fastcgi_index index.php;
        include fastcgi_params;
        fastcgi_param PHP_VALUE "upload_max_filesize=256M \n post_max_size=40M"; # Maximum size of an uploaded file (upload_max_filesize) and of a webserver request (post_max_size)
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        fastcgi_param HTTP_PROXY "";
        fastcgi_intercept_errors off;
        fastcgi_buffer_size 16k;
        fastcgi_buffers 4 16k;
        fastcgi_connect_timeout 300;
        fastcgi_send_timeout 300;
        fastcgi_read_timeout 300;
        include /etc/nginx/fastcgi_params;
    }

    set_real_ip_from 173.245.48.0/20;
    set_real_ip_from 103.21.244.0/22;
    set_real_ip_from 103.22.200.0/22;
    set_real_ip_from 103.31.4.0/22;
    set_real_ip_from 141.101.64.0/18;
    set_real_ip_from 108.162.192.0/18;
    set_real_ip_from 190.93.240.0/20;
    set_real_ip_from 188.114.96.0/20;
    set_real_ip_from 197.234.240.0/22;
    set_real_ip_from 198.41.128.0/17;
    set_real_ip_from 162.158.0.0/15;
    set_real_ip_from 104.16.0.0/13;
    set_real_ip_from 104.24.0.0/14;
    set_real_ip_from 172.64.0.0/13;
    set_real_ip_from 131.0.72.0/22;
    set_real_ip_from 2400:cb00::/32;
    set_real_ip_from 2606:4700::/32;
    set_real_ip_from 2803:f800::/32;
    set_real_ip_from 2405:b500::/32;
    set_real_ip_from 2405:8100::/32;
    set_real_ip_from 2a06:98c0::/29;
    set_real_ip_from 2c0f:f248::/32;
    real_ip_header CF-Connecting-IP;

    location ~ /\.ht {
        deny all;
    }
}
```
{% endcode %}

In this configuration, replace `path_site` with the path of your site in the `/var/www/` folder and `exemplu.dns` with your domain.
{% endtab %}

{% tab title="Proxy" %}
{% code title="nginx-proxy-web.conf" lineNumbers="true" %}
```nginx
server {
    listen 80;
    listen [::]:80;
    server_name exemplu.dns;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;
    listen [::]:443 ssl http2;
    server_name exemplu.dns;

    ssl_certificate /etc/letsencrypt/live/exemplu.dns/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/exemplu.dns/privkey.pem;
    ssl_session_cache shared:SSL:10m;
    ssl_protocols TLSv1.2 TLSv1.3;
    ssl_ciphers "ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384";
    ssl_prefer_server_ciphers on;

    location / {
        proxy_pass https://127.0.0.1:port;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection upgrade;
        proxy_set_header Accept-Encoding gzip;
    }

    set_real_ip_from 173.245.48.0/20;
    set_real_ip_from 103.21.244.0/22;
    set_real_ip_from 103.22.200.0/22;
    set_real_ip_from 103.31.4.0/22;
    set_real_ip_from 141.101.64.0/18;
    set_real_ip_from 108.162.192.0/18;
    set_real_ip_from 190.93.240.0/20;
    set_real_ip_from 188.114.96.0/20;
    set_real_ip_from 197.234.240.0/22;
    set_real_ip_from 198.41.128.0/17;
    set_real_ip_from 162.158.0.0/15;
    set_real_ip_from 104.16.0.0/13;
    set_real_ip_from 104.24.0.0/14;
    set_real_ip_from 172.64.0.0/13;
    set_real_ip_from 131.0.72.0/22;
    set_real_ip_from 2400:cb00::/32;
    set_real_ip_from 2606:4700::/32;
    set_real_ip_from 2803:f800::/32;
    set_real_ip_from 2405:b500::/32;
    set_real_ip_from 2405:8100::/32;
    set_real_ip_from 2a06:98c0::/29;
    set_real_ip_from 2c0f:f248::/32;
    real_ip_header CF-Connecting-IP;

    location ~ /\.ht {
        deny all;
    }
}
```
{% endcode %}

In this configuration, replace `port` with the port of the application you want to forward through the domain and `exemplu.dns` with your domain.
{% endtab %}
{% endtabs %}

Then press `CTRL + X`, `Y` and `ENTER` to save.
{% endstep %}

{% step %}
### Create the SSL certificate and enable the site

1. Stop Nginx first, so the certificates can be created:

   ```bash
   systemctl stop nginx
   ```

2. Create the SSL certificate with Certbot (replace `exemplu.dns` with the domain of your site):

   ```bash
   certbot certonly --standalone -d exemplu.dns
   ```

3. Give Nginx the right permissions on the site (replace `path_site` with the location of your site in `/var/www/`):

   ```bash
   chown -R www-data:www-data /var/www/path_site/*
   ```

4. Enable the site configuration (replace `<configname>` with the name you used in the previous step):

   ```bash
   rm /etc/nginx/sites-enabled/default && sudo ln -s /etc/nginx/sites-available/<configname>.conf /etc/nginx/sites-enabled/<configname>.conf
   ```
{% endstep %}

{% step %}
### Start Nginx

```bash
systemctl enable nginx && systemctl start nginx
```
{% endstep %}
{% endstepper %}

{% hint style="success" %}
Done. The site should now be online if the instructions were followed correctly.
{% endhint %}

{% hint style="info" %}
The `set_real_ip_from` lines in the configurations are Cloudflare's IP ranges, so Nginx sees your visitors' real IP when you use [Cloudflare](../../domains-web/cloudflare-domain.md).
{% endhint %}
