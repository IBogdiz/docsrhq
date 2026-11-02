---
description: "Create and configure an Unturned server on RHQ Game Hosting."
icon: person-walking
---

# Unturned server

Your Unturned server runs on our game panel (Pterodactyl). The first start downloads the game files through SteamCMD.

{% stepper %}
{% step %}
### Start the server

Open your server in the game panel and press **Start**. Wait until the console shows that the server is running.
{% endstep %}

{% step %}
### Set the basics

In the **Startup** tab set the server name, map (for example `PEI`) and maximum players.
{% endstep %}

{% step %}
### Configure it

Stop the server and edit the files in `Servers/<server name>/` from the **Files** tab. `Server/Commands.dat` holds commands such as `Name`, `Password`, `Mode` and `Map`; `Config.json` holds the gameplay settings.
{% endstep %}

{% step %}
### Join

In Unturned choose **Play → Connect**, enter `YOUR_SERVER_IP` and the game port (`27015` by default).
{% endstep %}
{% endstepper %}

## Ports

| Port | Protocol | Use |
|---|---|---|
| `27015` | UDP | Game connection |
| `27016` | UDP | Steam query (game port + 1) |

Your assigned ports are always visible in the panel and may differ from these defaults.

## Workshop mods

Add the Workshop item IDs to `WorkshopDownloadConfig.json` in the server folder and restart so the server downloads them.

{% hint style="info" %}
To get your server in the public list, a game server login token for App ID `304930` from [steamcommunity.com/dev/managegameservers](https://steamcommunity.com/dev/managegameservers) can be set in the **Startup** tab.
{% endhint %}
