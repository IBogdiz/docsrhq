---
description: "Creează și configurează un server dedicat Valheim la RHQ Game Hosting."
icon: axe
---

# Server Valheim

Serverul tău Valheim rulează pe panoul nostru de jocuri (Pterodactyl). La prima pornire se descarcă fișierele jocului, ceea ce poate dura câteva minute.

{% stepper %}
{% step %}
### Setează numele, lumea și parola

Deschide tabul **Startup** și completează numele serverului, numele lumii și o parolă.
{% endstep %}

{% step %}
### Pornește serverul

Apasă **Start** și așteaptă până când consola arată că lumea este încărcată.
{% endstep %}

{% step %}
### Conectează-te

În Valheim alege **Join Game → Join IP** și introdu `IP_SERVER:2456`. Poți adăuga și `IP_SERVER:2457` la favorite în lista de servere Steam.
{% endstep %}
{% endstepper %}

## Porturi

| Port | Protocol | Folosire |
|---|---|---|
| `2456` | UDP | Conexiunea la joc |
| `2457` | UDP | Lista de servere Steam (query) |
| `2458` | UDP | Rezervat de joc |

Porturile alocate ție sunt mereu vizibile în panou și pot diferi de cele implicite.

{% hint style="warning" %}
Parola trebuie să aibă cel puțin 5 caractere și nu are voie să facă parte din numele serverului sau al lumii, altfel serverul nu pornește.
{% endhint %}

## Backup-uri

Fișierele lumii se află în folderul de salvări afișat în tabul **Files** (fișiere `.db` și `.fwl`). Descarcă-le pe amândouă înainte de update-uri mari sau de schimbări de moduri.

## Moduri

Majoritatea modurilor Valheim au nevoie de BepInEx. Instalează-l pe server și pune modurile în `BepInEx/plugins`. Jucătorii au nevoie de aceleași moduri și pe client.
