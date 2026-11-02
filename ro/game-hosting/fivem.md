---
description: "Creează și configurează un server FiveM (GTA V) la RHQ Game Hosting."
icon: gamepad
---

# Server FiveM

FiveM este modificarea multiplayer pentru GTA V. Serverul tău rulează pe panoul nostru de jocuri (Pterodactyl).

{% stepper %}
{% step %}
### Obține o cheie de licență

Creează o cheie gratuită la [portal.cfx.re](https://portal.cfx.re), la **Server → Registration keys**, și copiaz-o.
{% endstep %}

{% step %}
### Introdu cheia în panou

Deschide serverul în panoul de jocuri, mergi la **Startup** și lipește cheia în câmpul de licență.
{% endstep %}

{% step %}
### Pornește serverul

Apasă **Start** și așteaptă să se termine încărcarea în consolă. La prima pornire se descarcă fișierele serverului.
{% endstep %}

{% step %}
### Configurează-l

În tabul **Files** editează `server.cfg`: setează `sv_hostname`, `sv_maxclients` și resursele pe care vrei să le pornești cu `ensure nume_resursa`.
{% endstep %}

{% step %}
### Conectează-te

Deschide FiveM, apasă **F8** și scrie:

```
connect IP_SERVER:30120
```
{% endstep %}
{% endstepper %}

## Porturi

| Port | Protocol | Folosire |
|---|---|---|
| `30120` | TCP și UDP | Conexiunea la joc |

Porturile alocate ție sunt mereu vizibile în panou și pot diferi de cele implicite.

## Adăugarea resurselor

Încarcă folderul resursei în `resources/`, din tabul **Files**, adaugă `ensure nume_folder` în `server.cfg` și repornește serverul.

{% hint style="info" %}
Vrei să rulezi FiveM pe propriul VPS? Vezi [FXServer pe Windows](fxserver-windows.md) sau [FXServer pe Linux](fxserver-linux.md).
{% endhint %}

{% hint style="warning" %}
Instalează resurse doar din surse în care ai încredere. O resursă rău intenționată poate rula cod pe serverul tău.
{% endhint %}
