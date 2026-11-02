---
description: "Create and configure a Garry's Mod server on RHQ Game Hosting."
icon: wrench
---

# Garry's Mod server

Your Garry's Mod server runs on our game panel (Pterodactyl). The first start downloads the game files through SteamCMD.

{% stepper %}
{% step %}
### Start the server

Open your server in the game panel and press **Start**. Wait until the console shows that the server is running.
{% endstep %}

{% step %}
### Choose gamemode and map

In the **Startup** tab set the gamemode (for example `sandbox`, `darkrp` or `terrortown`) and the start map.
{% endstep %}

{% step %}
### Configure it

In the **Files** tab edit `garrysmod/cfg/server.cfg`: `hostname`, `sv_password` and `rcon_password`.
{% endstep %}

{% step %}
### Join

In Garry's Mod open the console and type:

```
connect YOUR_SERVER_IP:27015
```
{% endstep %}
{% endstepper %}

## Ports

| Port | Protocol | Use |
|---|---|---|
| `27015` | UDP and TCP | Game connection and RCON |

Your assigned ports are always visible in the panel and may differ from these defaults.

## Addons and Workshop content

* Upload addons to `garrysmod/addons` from the **Files** tab.
* For Workshop content create a collection on Steam and enter its ID in the **Startup** tab. This needs a Steam Web API key from [steamcommunity.com/dev/apikey](https://steamcommunity.com/dev/apikey).

{% hint style="info" %}
Gamemodes such as DarkRP are separate downloads. Upload them to `garrysmod/gamemodes` and select them in **Startup**.
{% endhint %}
