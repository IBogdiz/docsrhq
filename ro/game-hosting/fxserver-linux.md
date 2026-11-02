---
description: "Instalează un FXServer FiveM pe Linux, pas cu pas."
icon: linux
---

# FXServer pe Linux

Acest ghid instalează un server FiveM (FXServer) pe un VPS sau server dedicat cu Linux.

## Cerințe

* **Git**, dacă vrei să urmezi modul recomandat de clonare a datelor serverului de bază.
* **Pachetul `xz` sau `xz-utils`.** Pe majoritatea sistemelor Linux este preinstalat.

## Instalare

{% stepper %}
{% step %}
### Creează dosarul serverului

Creează un dosar nou pentru fișierele binare ale serverului:

```bash
mkdir -p ~/FXServer/server
```
{% endstep %}

{% step %}
### Descarcă build-ul serverului

Descarcă versiunea curentă recomandată a ramurii master pentru Linux din lista de build-uri pentru serverul Linux. Copiază URL-ul versiunii recomandate și descarc-o cu `wget` (salveaz-o ca `fx.tar.xz`).
{% endstep %}

{% step %}
### Extrage arhiva

```bash
cd ~/FXServer/server && tar xf fx.tar.xz
```

Trebuie să ai `xz` instalat. Pe Debian/Ubuntu se află în pachetul `xz-utils`.
{% endstep %}

{% step %}
### Clonează datele serverului

Clonează `cfx-server-data` într-un dosar nou, în afara dosarului cu fișierele binare ale serverului:

```bash
git clone https://github.com/citizenfx/cfx-server-data.git ~/FXServer/server-data
```
{% endstep %}

{% step %}
### Creează server.cfg

Creează un fișier `server.cfg` în dosarul `server-data` și completează-l cu configurația de exemplu din documentația Cfx.re.
{% endstep %}

{% step %}
### Setează cheia de licență

Setează cheia ta de licență în `server.cfg`:

```
sv_licenseKey "licenseKeyGoesHere"
```

Poți crea o cheie la [portal.cfx.re](https://portal.cfx.re).
{% endstep %}

{% step %}
### Rulează serverul

Rulează serverul din dosarul `server-data`:

```bash
cd ~/FXServer/server-data && bash ~/FXServer/server/run.sh +exec server.cfg
```
{% endstep %}
{% endstepper %}

{% hint style="info" %}
Vrei o instalare mai rapidă? [RHQ Game Installer](../vps-dedicated/linux/rhq-game-installer.md) instalează FiveM cu o singură comandă.
{% endhint %}
