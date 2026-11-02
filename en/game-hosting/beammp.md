---
description: "Create and configure a BeamMP (BeamNG.drive multiplayer) server on RHQ Game Hosting."
icon: car
---

# BeamMP server

BeamMP adds multiplayer to BeamNG.drive. Your server runs on our game panel (Pterodactyl).

{% stepper %}
{% step %}
### Get an AuthKey

Log in at [keymaster.beammp.com](https://keymaster.beammp.com) with your BeamMP account and create a server key.
{% endstep %}

{% step %}
### Enter the key in the panel

Open your server in the game panel, go to **Startup** and paste the key in the AuthKey field. Alternatively set `AuthKey` in `ServerConfig.toml`.
{% endstep %}

{% step %}
### Start the server

Press **Start** and wait until the console shows that the server is running.
{% endstep %}

{% step %}
### Configure it

In the **Files** tab edit `ServerConfig.toml`: `Name`, `MaxPlayers`, `Map`, `Description` and `Private`.
{% endstep %}

{% step %}
### Join

Open the BeamMP launcher, find your server in the list (or use **Direct connect**) and join.
{% endstep %}
{% endstepper %}

## Ports

| Port | Protocol | Use |
|---|---|---|
| `30814` | TCP and UDP | Game connection |

Your assigned ports are always visible in the panel and may differ from these defaults.

## Mods and scripts

* Client mods (`.zip`) go in `Resources/Client`.
* Server plugins (Lua) go in `Resources/Server/<plugin name>`.

Restart after changes. Players download client mods automatically when they join.

{% hint style="info" %}
The map is set with its path, for example `/levels/gridmap_v2/info.json`.
{% endhint %}
