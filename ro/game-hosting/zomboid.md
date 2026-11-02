---
description: "Creează și configurează un server Project Zomboid la RHQ Game Hosting."
icon: skull
---

# Server Project Zomboid

Serverul tău Project Zomboid rulează pe panoul nostru de jocuri (Pterodactyl). La prima pornire se descarcă fișierele jocului și se generează lumea, ceea ce poate dura câteva minute.

{% stepper %}
{% step %}
### Setează parola de admin

Deschide tabul **Startup** și setează parola de administrator. Serverul o cere la prima pornire.
{% endstep %}

{% step %}
### Pornește serverul

Apasă **Start** și așteaptă până când consola arată că serverul rulează.
{% endstep %}

{% step %}
### Configurează-l

În tabul **Files** editează `Zomboid/Server/servertest.ini` (numele depinde de numele serverului): `PublicName`, `MaxPlayers`, `Password` și `PVP`. Oprește mai întâi serverul, altfel poate suprascrie modificările.
{% endstep %}

{% step %}
### Conectează-te

În Project Zomboid alege **Join**, adaugă un server cu `IP_SERVER` și portul `16261`.
{% endstep %}
{% endstepper %}

## Porturi

| Port | Protocol | Folosire |
|---|---|---|
| `16261` | UDP | Conexiunea la joc |
| `16262` | UDP | Conexiune directă |

Porturile alocate ție sunt mereu vizibile în panou și pot diferi de cele implicite.

## Moduri

Găsești ID-ul itemului Workshop în URL-ul paginii Steam a modului, iar ID-ul modului în descriere. Adaugă-le în `servertest.ini`:

```ini
WorkshopItems=ID_WORKSHOP_1;ID_WORKSHOP_2
Mods=ModID1;ModID2
```

Repornește serverul ca să descarce modurile.

{% hint style="info" %}
Jocul folosește și un interval de porturi UDP care începe după `16262`, câte unul pentru fiecare jucător conectat. Intervalul tău este afișat în panou.
{% endhint %}
