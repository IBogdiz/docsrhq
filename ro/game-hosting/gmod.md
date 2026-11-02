---
description: "Creează și configurează un server Garry's Mod la RHQ Game Hosting."
icon: wrench
---

# Server Garry's Mod

Serverul tău Garry's Mod rulează pe panoul nostru de jocuri (Pterodactyl). La prima pornire se descarcă fișierele jocului prin SteamCMD.

{% stepper %}
{% step %}
### Pornește serverul

Deschide serverul în panoul de jocuri și apasă **Start**. Așteaptă până când consola arată că serverul rulează.
{% endstep %}

{% step %}
### Alege modul de joc și harta

În tabul **Startup** setează modul de joc (de exemplu `sandbox`, `darkrp` sau `terrortown`) și harta de start.
{% endstep %}

{% step %}
### Configurează-l

În tabul **Files** editează `garrysmod/cfg/server.cfg`: `hostname`, `sv_password` și `rcon_password`.
{% endstep %}

{% step %}
### Conectează-te

În Garry's Mod deschide consola și scrie:

```
connect IP_SERVER:27015
```
{% endstep %}
{% endstepper %}

## Porturi

| Port | Protocol | Folosire |
|---|---|---|
| `27015` | UDP și TCP | Conexiunea la joc și RCON |

Porturile alocate ție sunt mereu vizibile în panou și pot diferi de cele implicite.

## Addonuri și conținut Workshop

* Încarcă addonurile în `garrysmod/addons`, din tabul **Files**.
* Pentru conținut Workshop creează o colecție pe Steam și introdu ID-ul ei în tabul **Startup**. Ai nevoie de o cheie Steam Web API de la [steamcommunity.com/dev/apikey](https://steamcommunity.com/dev/apikey).

{% hint style="info" %}
Modurile de joc precum DarkRP se descarcă separat. Încarcă-le în `garrysmod/gamemodes` și alege-le în **Startup**.
{% endhint %}
