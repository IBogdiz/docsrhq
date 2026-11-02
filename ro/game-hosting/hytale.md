---
description: "Creează și configurează un server Hytale la RHQ Game Hosting."
icon: dragon
---

# Server Hytale

Serverul tău Hytale rulează pe panoul nostru de jocuri (Pterodactyl). Serverele Hytale rulează pe Java 25 și au nevoie de cel puțin 4 GB de memorie.

{% stepper %}
{% step %}
### Pornește serverul

Deschide serverul în panoul de jocuri și apasă **Start**. Așteaptă până când consola este gata de comenzi.
{% endstep %}

{% step %}
### Autentifică serverul

În **Console** scrie `/auth login device`. Deschide [accounts.hytale.com/device](https://accounts.hytale.com/device), introdu codul afișat și confirmă. Codul expiră după 15 minute.
{% endstep %}

{% step %}
### Configurează-l

Oprește serverul și editează `config.json` în tabul **Files**. Whitelistul, permisiunile și banurile sunt în `whitelist.json`, `permissions.json` și `bans.json`.
{% endstep %}

{% step %}
### Conectează-te

În Hytale alege conectarea la un server prin adresă și introdu `IP_SERVER:5520`.
{% endstep %}
{% endstepper %}

## Porturi

| Port | Protocol | Folosire |
|---|---|---|
| `5520` | UDP | Conexiunea la joc (QUIC) |

Porturile alocate ție sunt mereu vizibile în panou și pot diferi de cele implicite.

## Moduri

Încarcă fișierele modurilor (`.zip` sau `.jar`) în folderul `mods/` și repornește serverul.

{% hint style="warning" %}
Hytale folosește **doar UDP**. Dacă deschizi un port într-un firewall, permite UDP, nu TCP.
{% endhint %}

{% hint style="info" %}
Serverul citește fișierele la pornire și le rescrie în timpul jocului, deci modificările făcute cât rulează pot fi suprascrise. Oprește mereu serverul înainte să editezi. O singură licență Hytale poate autentifica până la 500 de servere.
{% endhint %}
