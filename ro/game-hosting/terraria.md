---
description: "Creează și configurează un server Terraria (TShock) la RHQ Game Hosting."
icon: pickaxe
---

# Server Terraria

Serverul tău Terraria rulează pe panoul nostru de jocuri (Pterodactyl) și rulează TShock, care adaugă unelte de administrare și permisiuni.

{% stepper %}
{% step %}
### Pornește serverul

Deschide serverul în panoul de jocuri și apasă **Start**. La prima pornire generează o lume și scrie configurația.
{% endstep %}

{% step %}
### Setează elementele de bază

În tabul **Startup** setează numele lumii, mărimea, dificultatea, numărul maxim de jucători și parola.
{% endstep %}

{% step %}
### Fă-te administrator

Consola afișează un cod de setup la prima pornire. Intră pe server, scrie `/setup COD` în chat, apoi creează-ți contul cu `/user add NUME PAROLA owner` în **Console**.
{% endstep %}

{% step %}
### Conectează-te

În Terraria alege **Multiplayer → Join via IP** și introdu `IP_SERVER` și portul `7777`.
{% endstep %}
{% endstepper %}

## Porturi

| Port | Protocol | Folosire |
|---|---|---|
| `7777` | TCP | Conexiunea la joc |

Porturile alocate ție sunt mereu vizibile în panou și pot diferi de cele implicite.

## Configurare

Setările TShock sunt în `tshock/config.json`, în tabul **Files**. Editează-le cât timp serverul este oprit.

## Pluginuri

Încarcă pluginurile TShock (`.dll`) în `ServerPlugins` și repornește serverul.
