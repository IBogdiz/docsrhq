---
description: "Creează și configurează un server RedM (Red Dead Redemption 2) la RHQ Game Hosting."
icon: hat-cowboy
---

# Server RedM

RedM este modificarea multiplayer pentru Red Dead Redemption 2, construită pe aceeași tehnologie ca FiveM. Serverul tău rulează pe panoul nostru de jocuri (Pterodactyl).

{% stepper %}
{% step %}
### Obține o cheie de licență

Creează o cheie gratuită la [portal.cfx.re](https://portal.cfx.re) în **Server → Registration keys** și copiaz-o.
{% endstep %}

{% step %}
### Introdu cheia în panou

Deschide serverul în panoul de jocuri, intră la **Startup** și lipește cheia în câmpul de licență.
{% endstep %}

{% step %}
### Pornește serverul

Apasă **Start** și așteaptă să se încarce consola. La prima pornire se descarcă fișierele serverului.
{% endstep %}

{% step %}
### Configurează-l

În tabul **Files** editează `server.cfg`: setează `sv_hostname`, `sv_maxclients` și resursele pe care vrei să le pornești cu `ensure nume_resursa`.
{% endstep %}

{% step %}
### Conectează-te

Deschide RedM, apasă **F8** și scrie:

```
connect IP_SERVER:30120
```
{% endstep %}
{% endstepper %}

## Porturi

| Port | Protocol | Utilizare |
|---|---|---|
| `30120` | TCP și UDP | Conexiunea la joc |

## Adaugă resurse

Încarcă folderul resursei în `resources/` din tabul **Files**, adaugă `ensure nume_folder` în `server.cfg` și repornește.

{% hint style="warning" %}
Instalează resurse doar din surse în care ai încredere. O resursă malițioasă poate rula cod pe serverul tău.
{% endhint %}
