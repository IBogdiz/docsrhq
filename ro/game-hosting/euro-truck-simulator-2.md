---
description: "Creează și configurează un server dedicat Euro Truck Simulator 2 la RHQ Game Hosting."
icon: truck
---

# Server Euro Truck Simulator 2

Pornește propriul server de convoi Euro Truck Simulator 2 pe panoul nostru de jocuri (Pterodactyl).

{% stepper %}
{% step %}
### Creează un token de server

Jocul cere un token de server (`server_token` al serverului dedicat). Generează-l din pagina de conturi de server Steam sau din modul de multiplayer pe care îl folosești și copiaz-o.
{% endstep %}

{% step %}
### Introdu tokenul

Deschide serverul în panoul de jocuri, intră la **Startup** și lipește tokenul în câmpul potrivit. Setează în același timp numele serverului și numărul maxim de jucători.
{% endstep %}

{% step %}
### Pornește serverul

Apasă **Start**. La prima pornire se descarcă fișierele serverului dedicat.
{% endstep %}

{% step %}
### Conectează-te

Pornește jocul, deschide **Convoy** (multiplayer) și caută numele serverului în listă sau conectează-te cu IP-ul și portul.
{% endstep %}
{% endstepper %}

## Porturi

| Port | Protocol | Utilizare |
|---|---|---|
| `27015` | UDP | Conexiunea la joc |
| `27016` | UDP | Query (lista de servere) |

Porturile tale alocate sunt afișate în panou și pot diferi de cele implicite.

{% hint style="info" %}
Serverul dedicat și jocul trebuie să aibă aceeași versiune. După o actualizare a jocului, repornește serverul ca să se actualizeze și el.
{% endhint %}
