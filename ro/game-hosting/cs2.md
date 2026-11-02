---
description: "Creează și configurează un server Counter-Strike 2 la RHQ Game Hosting."
icon: crosshairs
---

# Server Counter-Strike 2

Serverul tău Counter-Strike 2 rulează pe panoul nostru de jocuri (Pterodactyl). La prima pornire se descarcă fișierele jocului prin SteamCMD, deci durează mai mult decât pornirile următoare.

{% stepper %}
{% step %}
### Obține un token de server

Autentifică-te la [steamcommunity.com/dev/managegameservers](https://steamcommunity.com/dev/managegameservers), introdu App ID `730` și creează un token (GSLT). Fără el serverul nu apare public în listă.
{% endstep %}

{% step %}
### Introdu tokenul în panou

Deschide serverul, mergi la **Startup** și lipește tokenul în câmpul pentru tokenul Steam.
{% endstep %}

{% step %}
### Pornește serverul

Apasă **Start** și așteaptă până când consola arată că serverul rulează.
{% endstep %}

{% step %}
### Setează elementele de bază

În tabul **Files** editează `game/csgo/cfg/server.cfg`: `hostname`, `sv_password`, `rcon_password`. Harta de start și modul de joc se setează în **Startup**.
{% endstep %}

{% step %}
### Conectează-te

În CS2 deschide consola (`~`) și scrie:

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

## Comenzi utile în consolă

```
changelevel de_dust2
host_workshop_map ID_WORKSHOP
mp_restartgame 1
```

## Pluginuri

Pluginurile CS2 rulează pe Metamod, cu un framework precum CounterStrikeSharp. Încarcă-le în `game/csgo/addons`, din tabul **Files**, și urmează instrucțiunile pluginului.

{% hint style="warning" %}
Setează un `rcon_password` puternic. Oricine îl știe poate controla complet serverul tău.
{% endhint %}
