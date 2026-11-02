---
description: "Create and configure a Counter-Strike 2 server on RHQ Game Hosting."
icon: crosshairs
---

# Counter-Strike 2 server

Your Counter-Strike 2 server runs on our game panel (Pterodactyl). The first start downloads the game files through SteamCMD, so it takes longer than later starts.

{% stepper %}
{% step %}
### Get a game server token

Log in at [steamcommunity.com/dev/managegameservers](https://steamcommunity.com/dev/managegameservers), enter App ID `730` and create a token (GSLT). Without it the server is not listed publicly.
{% endstep %}

{% step %}
### Enter the token in the panel

Open your server, go to **Startup** and paste the token in the Steam token field.
{% endstep %}

{% step %}
### Start the server

Press **Start** and wait until the console shows that the server is running.
{% endstep %}

{% step %}
### Set the basics

In the **Files** tab edit `game/csgo/cfg/server.cfg`: `hostname`, `sv_password`, `rcon_password`. Set the start map and game mode in **Startup**.
{% endstep %}

{% step %}
### Join

In CS2 open the console (`~`) and type:

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

## Useful console commands

```
changelevel de_dust2
host_workshop_map WORKSHOP_ID
mp_restartgame 1
```

## Plugins

CS2 plugins run on Metamod with a framework such as CounterStrikeSharp. Upload them to `game/csgo/addons` from the **Files** tab and follow the plugin's instructions.

{% hint style="warning" %}
Set a strong `rcon_password`. Anyone who knows it can fully control your server.
{% endhint %}
