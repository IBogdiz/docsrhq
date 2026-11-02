---
description: "Install PHP 8.1 (or any other version) on Debian or Ubuntu."
icon: php
---

# Install PHP

Pick your operating system below. In the commands, `8.1` can be replaced with any valid PHP version.

{% tabs %}
{% tab title="Debian 11/12" %}
Add the PHP repository for Debian:

```bash
echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/sury-php.list
curl -fsSL https://packages.sury.org/php/apt.gpg | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/sury-keyring.gpg
```

Update the repositories and install PHP 8.1:

```bash
apt update -y
apt install -y php8.1 php8.1-{common,cli,gd,mysql,mbstring,bcmath,xml,fpm,curl,zip}
```
{% endtab %}

{% tab title="Ubuntu 20.04/22.04" %}
Add the PHP repository for Ubuntu:

```bash
apt -y install software-properties-common curl apt-transport-https ca-certificates gnupg
LC_ALL=C.UTF-8 add-apt-repository -y ppa:ondrej/php
```

Update the repositories and install PHP 8.1:

```bash
apt update
apt -y install php8.1 php8.1-{common,cli,gd,mysql,mbstring,bcmath,xml,fpm,curl,zip}
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Planning to host a website? Continue with [Nginx configuration](nginx-config.md).
{% endhint %}
