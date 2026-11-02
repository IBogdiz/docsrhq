---
description: "Creează și configurează un server Rust la RHQ Game Hosting."
icon: gamepad
---

# Server Rust

Serverul tău Rust rulează pe panoul nostru de jocuri (Pterodactyl). Se instalează automat după achiziție.

{% stepper %}
{% step %}
### Deschide panoul

Autentifică-te în panoul de jocuri cu linkul din emailul serviciului și alege serverul Rust.
{% endstep %}

{% step %}
### Pornește serverul

Apasă **Start**. La prima pornire se descarcă fișierele jocului și poate dura câteva minute. Așteaptă până când consola arată că serverul rulează.
{% endstep %}

{% step %}
### Setează elementele de bază

Deschide tabul **Startup** și setează numele serverului, descrierea, numărul maxim de jucători, dimensiunea hărții și seed-ul.
{% endstep %}

{% step %}
### Conectează-te

În Rust apasă **F1** și scrie:

```
client.connect IP_SERVER:28015
```

Înlocuiește IP-ul și portul cu cele afișate în pagina **Console** a serverului tău.
{% endstep %}
{% endstepper %}

## Porturi

| Port | Protocol | Utilizare |
|---|---|---|
| `28015` | UDP | Conexiunea la joc |
| `28016` | TCP | RCON (consolă la distanță) |
| `28082` | TCP | Aplicația Rust+ |

Porturile tale alocate sunt mereu vizibile în panou și pot diferi de cele implicite.

## Pluginuri (Oxide/uMod)

Instalează Oxide din tabul **Startup** (sau încarcă-l din tabul **Files**), apoi pune fișierele `.cs` ale pluginurilor în `oxide/plugins` și se încarcă automat.

{% hint style="info" %}
După un forced wipe Rust (prima joi din fiecare lună) actualizează serverul înainte să îl pornești, altfel jucătorii nu se pot conecta.
{% endhint %}
