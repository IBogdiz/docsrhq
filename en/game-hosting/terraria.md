---
description: "Create and configure a Terraria (TShock) server on RHQ Game Hosting."
icon: pickaxe
---

# Terraria server

Your Terraria server runs on our game panel (Pterodactyl) and runs TShock, which adds administration tools and permissions.

{% stepper %}
{% step %}
### Start the server

Open your server in the game panel and press **Start**. On the first start it generates a world and writes the configuration.
{% endstep %}

{% step %}
### Set the basics

In the **Startup** tab set the world name, size, difficulty, maximum players and password.
{% endstep %}

{% step %}
### Make yourself admin

The console prints a setup code on the first start. Join the server, type `/setup CODE` in chat, then create your account with `/user add NAME PASSWORD owner` in the **Console**.
{% endstep %}

{% step %}
### Join

In Terraria choose **Multiplayer → Join via IP** and enter `YOUR_SERVER_IP` and port `7777`.
{% endstep %}
{% endstepper %}

## Ports

| Port | Protocol | Use |
|---|---|---|
| `7777` | TCP | Game connection |

Your assigned ports are always visible in the panel and may differ from these defaults.

## Configuration

TShock settings are in `tshock/config.json` in the **Files** tab. Edit them while the server is stopped.

## Plugins

Upload TShock plugins (`.dll`) to `ServerPlugins` and restart.
