---
description: "Instalează PHP 8.1 (sau altă versiune) pe Debian sau Ubuntu."
icon: php
---

# Instalarea PHP

Alege mai jos sistemul tău de operare. În comenzi, `8.1` poate fi înlocuit cu orice versiune validă de PHP.

{% tabs %}
{% tab title="Debian 11/12" %}
Adaugă repository-ul PHP pentru Debian:

```bash
echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/sury-php.list
curl -fsSL https://packages.sury.org/php/apt.gpg | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/sury-keyring.gpg
```

Actualizează repository-urile și instalează PHP 8.1:

```bash
apt update -y
apt install -y php8.1 php8.1-{common,cli,gd,mysql,mbstring,bcmath,xml,fpm,curl,zip}
```
{% endtab %}

{% tab title="Ubuntu 20.04/22.04" %}
Adaugă repository-ul PHP pentru Ubuntu:

```bash
apt -y install software-properties-common curl apt-transport-https ca-certificates gnupg
LC_ALL=C.UTF-8 add-apt-repository -y ppa:ondrej/php
```

Actualizează repository-urile și instalează PHP 8.1:

```bash
apt update
apt -y install php8.1 php8.1-{common,cli,gd,mysql,mbstring,bcmath,xml,fpm,curl,zip}
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Vrei să găzduiești un site? Continuă cu [Configurarea Nginx](nginx-config.md).
{% endhint %}
