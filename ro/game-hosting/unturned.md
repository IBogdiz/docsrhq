---
description: "Creează și configurează un server Unturned la RHQ Game Hosting."
icon: person-walking
---

# Server Unturned

Serverul tău Unturned rulează pe panoul nostru de jocuri (Pterodactyl). La prima pornire se descarcă fișierele jocului prin SteamCMD.

{% stepper %}
{% step %}
### Pornește serverul

Deschide serverul în panoul de jocuri și apasă **Start**. Așteaptă până când consola arată că serverul rulează.
{% endstep %}

{% step %}
### Setează elementele de bază

În tabul **Startup** setează numele serverului, harta (de exemplu `PEI`) și numărul maxim de jucători.
{% endstep %}

{% step %}
### Configurează-l

Oprește serverul și editează fișierele din `Servers/<nume server>/`, în tabul **Files**. `Server/Commands.dat` conține comenzi precum `Name`, `Password`, `Mode` și `Map`; `Config.json` conține setările de gameplay.
{% endstep %}

{% step %}
### Conectează-te

În Unturned alege **Play → Connect**, introdu `IP_SERVER` și portul jocului (`27015` implicit).
{% endstep %}
{% endstepper %}

## Porturi

| Port | Protocol | Folosire |
|---|---|---|
| `27015` | UDP | Conexiunea la joc |
| `27016` | UDP | Steam query (portul jocului + 1) |

Porturile alocate ție sunt mereu vizibile în panou și pot diferi de cele implicite.

## Moduri Workshop

Adaugă ID-urile itemelor Workshop în `WorkshopDownloadConfig.json`, în folderul serverului, și repornește ca serverul să le descarce.

{% hint style="info" %}
Ca serverul să apară în lista publică, poți seta în tabul **Startup** un token de login pentru App ID `304930`, de la [steamcommunity.com/dev/managegameservers](https://steamcommunity.com/dev/managegameservers).
{% endhint %}
