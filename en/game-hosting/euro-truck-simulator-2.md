---
description: "Create and configure a Euro Truck Simulator 2 dedicated server on RHQ Game Hosting."
icon: truck
---

# Euro Truck Simulator 2 server

Run your own Euro Truck Simulator 2 convoy server on our game panel (Pterodactyl).

{% stepper %}
{% step %}
### Create a server token

The game requires a server token (the `server_token` of the dedicated server). Generate it from the Steam game server account page or from the multiplayer mod you use, and copy it.
{% endstep %}

{% step %}
### Enter the token

Open your server in the game panel, go to **Startup** and paste the token in the matching field. Set the server name and maximum players at the same time.
{% endstep %}

{% step %}
### Start the server

Press **Start**. The first start downloads the dedicated server files.
{% endstep %}

{% step %}
### Join

Start the game, open **Convoy** (multiplayer) and search your server name in the list, or connect with its IP and port.
{% endstep %}
{% endstepper %}

## Ports

| Port | Protocol | Use |
|---|---|---|
| `27015` | UDP | Game connection |
| `27016` | UDP | Query (server list) |

Your assigned ports are shown in the panel and may differ from these defaults.

{% hint style="info" %}
The dedicated server and the game must be on the same game version. After a game update, restart the server so it updates too.
{% endhint %}
