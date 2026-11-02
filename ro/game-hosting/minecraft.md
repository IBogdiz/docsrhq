---
description: "Creează și configurează un server Minecraft Java la RHQ Game Hosting."
icon: cube
---

# Server Minecraft

Serverul tău Minecraft Java rulează pe panoul nostru de jocuri (Pterodactyl). Se instalează automat după achiziție.

{% stepper %}
{% step %}
### Deschide panoul

Autentifică-te în panoul de jocuri cu linkul din emailul serviciului și alege serverul Minecraft.
{% endstep %}

{% step %}
### Acceptă EULA

În tabul **Files** deschide `eula.txt`, setează `eula=true` și salvează. Serverul nu pornește fără asta.
{% endstep %}

{% step %}
### Alege versiunea

Deschide tabul **Startup** și alege versiunea de Minecraft (și tipul de server, dacă e oferit).
{% endstep %}

{% step %}
### Pornește serverul

Apasă **Start**. La prima pornire se descarcă serverul și se generează lumea, ceea ce poate dura un minut sau două.
{% endstep %}

{% step %}
### Conectează-te

În Minecraft mergi la **Multiplayer → Add Server** și introdu `IP_SERVER:25565`.
{% endstep %}
{% endstepper %}

## Porturi

| Port | Protocol | Folosire |
|---|---|---|
| `25565` | TCP | Conexiunea la joc |

Porturile alocate ție sunt mereu vizibile în panou și pot diferi de cele implicite.

## Setări

În tabul **Files** editează `server.properties` și repornește serverul. Cele mai folosite opțiuni:

| Opțiune | Ce face |
|---|---|
| `motd` | Textul afișat în lista de servere |
| `max-players` | Numărul maxim de jucători |
| `difficulty` | `peaceful`, `easy`, `normal` sau `hard` |
| `white-list` | `true` ca să intre doar jucătorii din listă |
| `online-mode` | `true` verifică jucătorii cu conturile Minecraft |

## Operatori și whitelist

Scrie în **Console** (fără `/`):

```
op NumeJucator
whitelist add NumeJucator
```

## Pluginuri

Pe serverele Paper sau Spigot încarcă fișierele `.jar` ale pluginurilor în `plugins/` și repornește serverul.

{% hint style="warning" %}
Păstrează `online-mode=true`. Cu `false` oricine poate intra cu orice nume, inclusiv al tău.
{% endhint %}
