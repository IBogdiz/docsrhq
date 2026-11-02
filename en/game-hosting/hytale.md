---
description: "Create and configure a Hytale server on RHQ Game Hosting."
icon: dragon
---

# Hytale server

Your Hytale server runs on our game panel (Pterodactyl). Hytale servers run on Java 25 and need at least 4 GB of memory.

{% stepper %}
{% step %}
### Start the server

Open your server in the game panel and press **Start**. Wait until the console is ready for commands.
{% endstep %}

{% step %}
### Authenticate the server

In the **Console** type `/auth login device`. Open [accounts.hytale.com/device](https://accounts.hytale.com/device), enter the code shown and confirm. The code expires after 15 minutes.
{% endstep %}

{% step %}
### Configure it

Stop the server and edit `config.json` in the **Files** tab. Whitelist, permissions and bans are in `whitelist.json`, `permissions.json` and `bans.json`.
{% endstep %}

{% step %}
### Join

In Hytale choose to connect to a server by address and enter `YOUR_SERVER_IP:5520`.
{% endstep %}
{% endstepper %}

## Ports

| Port | Protocol | Use |
|---|---|---|
| `5520` | UDP | Game connection (QUIC) |

Your assigned ports are always visible in the panel and may differ from these defaults.

## Mods

Upload mod files (`.zip` or `.jar`) to the `mods/` folder and restart.

{% hint style="warning" %}
Hytale uses **UDP only**. If you forward or allow a port in a firewall, allow UDP, not TCP.
{% endhint %}

{% hint style="info" %}
The server reads its files at start and rewrites them during play, so edits made while it runs can be overwritten. Always stop the server before editing. A single Hytale license can authenticate up to 500 servers.
{% endhint %}
