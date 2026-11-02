---
description: "Creează și configurează un server BeamMP (multiplayer pentru BeamNG.drive) la RHQ Game Hosting."
icon: car
---

# Server BeamMP

BeamMP adaugă multiplayer în BeamNG.drive. Serverul tău rulează pe panoul nostru de jocuri (Pterodactyl).

{% stepper %}
{% step %}
### Obține un AuthKey

Autentifică-te la [keymaster.beammp.com](https://keymaster.beammp.com) cu contul tău BeamMP și creează o cheie de server.
{% endstep %}

{% step %}
### Introdu cheia în panou

Deschide serverul în panoul de jocuri, mergi la **Startup** și lipește cheia în câmpul AuthKey. Alternativ, setează `AuthKey` în `ServerConfig.toml`.
{% endstep %}

{% step %}
### Pornește serverul

Apasă **Start** și așteaptă până când consola arată că serverul rulează.
{% endstep %}

{% step %}
### Configurează-l

În tabul **Files** editează `ServerConfig.toml`: `Name`, `MaxPlayers`, `Map`, `Description` și `Private`.
{% endstep %}

{% step %}
### Conectează-te

Deschide launcherul BeamMP, găsește serverul în listă (sau folosește **Direct connect**) și intră.
{% endstep %}
{% endstepper %}

## Porturi

| Port | Protocol | Folosire |
|---|---|---|
| `30814` | TCP și UDP | Conexiunea la joc |

Porturile alocate ție sunt mereu vizibile în panou și pot diferi de cele implicite.

## Moduri și scripturi

* Modurile pentru client (`.zip`) merg în `Resources/Client`.
* Pluginurile de server (Lua) merg în `Resources/Server/<nume plugin>`.

Repornește după modificări. Jucătorii descarcă automat modurile de client când intră.

{% hint style="info" %}
Harta se setează cu calea ei, de exemplu `/levels/gridmap_v2/info.json`.
{% endhint %}
