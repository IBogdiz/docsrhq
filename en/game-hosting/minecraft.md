---
description: "Create and configure a Minecraft Java server on RHQ Game Hosting."
icon: cube
---

# Minecraft server

Your Minecraft Java server runs on our game panel (Pterodactyl). It installs automatically after purchase.

{% stepper %}
{% step %}
### Open the panel

Log in to the game panel with the link in your service email and select your Minecraft server.
{% endstep %}

{% step %}
### Accept the EULA

In the **Files** tab open `eula.txt`, set `eula=true` and save. The server refuses to start without it.
{% endstep %}

{% step %}
### Choose the version

Open the **Startup** tab and pick the Minecraft version (and server type, if offered).
{% endstep %}

{% step %}
### Start the server

Press **Start**. The first start downloads the server and generates the world, which can take a minute or two.
{% endstep %}

{% step %}
### Join

In Minecraft go to **Multiplayer → Add Server** and enter `YOUR_SERVER_IP:25565`.
{% endstep %}
{% endstepper %}

## Ports

| Port | Protocol | Use |
|---|---|---|
| `25565` | TCP | Game connection |

Your assigned ports are always visible in the panel and may differ from these defaults.

## Settings

In the **Files** tab edit `server.properties` and restart. The most used options:

| Option | What it does |
|---|---|
| `motd` | Text shown in the server list |
| `max-players` | Maximum number of players |
| `difficulty` | `peaceful`, `easy`, `normal` or `hard` |
| `white-list` | `true` to allow only listed players |
| `online-mode` | `true` checks players against Minecraft accounts |

## Operators and whitelist

Type these in the **Console** (without `/`):

```
op PlayerName
whitelist add PlayerName
```

## Plugins

On Paper or Spigot servers upload plugin `.jar` files into `plugins/` and restart.

{% hint style="warning" %}
Keep `online-mode=true`. Setting it to `false` lets anyone join with any name, including yours.
{% endhint %}
