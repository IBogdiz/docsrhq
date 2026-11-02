---
description: "Create and configure a Project Zomboid server on RHQ Game Hosting."
icon: skull
---

# Project Zomboid server

Your Project Zomboid server runs on our game panel (Pterodactyl). The first start downloads the game files and generates the world, which can take several minutes.

{% stepper %}
{% step %}
### Set the admin password

Open the **Startup** tab and set the admin password. The server asks for it on the first start.
{% endstep %}

{% step %}
### Start the server

Press **Start** and wait until the console shows that the server is running.
{% endstep %}

{% step %}
### Configure it

In the **Files** tab edit `Zomboid/Server/servertest.ini` (the name depends on your server name): `PublicName`, `MaxPlayers`, `Password` and `PVP`. Stop the server first, otherwise it may overwrite your edits.
{% endstep %}

{% step %}
### Join

In Project Zomboid choose **Join**, add a server with `YOUR_SERVER_IP` and port `16261`.
{% endstep %}
{% endstepper %}

## Ports

| Port | Protocol | Use |
|---|---|---|
| `16261` | UDP | Game connection |
| `16262` | UDP | Direct connection |

Your assigned ports are always visible in the panel and may differ from these defaults.

## Mods

Find the Workshop item ID in the mod's Steam page URL and the mod ID in its description. Add them to `servertest.ini`:

```ini
WorkshopItems=WORKSHOP_ID_1;WORKSHOP_ID_2
Mods=ModID1;ModID2
```

Restart the server so it downloads the mods.

{% hint style="info" %}
The game also uses a range of UDP ports starting after `16262`, one per connected player. Your assigned range is shown in the panel.
{% endhint %}
