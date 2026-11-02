---
description: "Create and configure a Valheim dedicated server on RHQ Game Hosting."
icon: axe
---

# Valheim server

Your Valheim server runs on our game panel (Pterodactyl). The first start downloads the game files, which can take several minutes.

{% stepper %}
{% step %}
### Set name, world and password

Open the **Startup** tab and fill in the server name, the world name and a password.
{% endstep %}

{% step %}
### Start the server

Press **Start** and wait until the console shows that the world is loaded.
{% endstep %}

{% step %}
### Join

In Valheim choose **Join Game → Join IP** and enter `YOUR_SERVER_IP:2456`. You can also add `YOUR_SERVER_IP:2457` as a favourite in the Steam server browser.
{% endstep %}
{% endstepper %}

## Ports

| Port | Protocol | Use |
|---|---|---|
| `2456` | UDP | Game connection |
| `2457` | UDP | Steam server list (query) |
| `2458` | UDP | Reserved by the game |

Your assigned ports are always visible in the panel and may differ from these defaults.

{% hint style="warning" %}
The password must be at least 5 characters long and must not be part of the server name or world name, or the server will not start.
{% endhint %}

## Backups

World files are stored in the save folder shown in the **Files** tab (`.db` and `.fwl` files). Download both before major updates or mod changes.

## Mods

Most Valheim mods need BepInEx. Install it on the server and put the mods in `BepInEx/plugins`. Players need the same client-side mods.
