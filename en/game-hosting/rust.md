---
description: "Create and configure a Rust game server on RHQ Game Hosting."
icon: gamepad
---

# Rust server

Your Rust server runs on our game panel (Pterodactyl). It installs automatically after purchase.

{% stepper %}
{% step %}
### Open the panel

Log in to the game panel with the link in your service email and select your Rust server.
{% endstep %}

{% step %}
### Start the server

Press **Start**. The first start downloads the game files and can take several minutes. Wait until the console shows that the server is running.
{% endstep %}

{% step %}
### Set the basics

Open the **Startup** tab and set the server name, description, maximum players, world size and seed.
{% endstep %}

{% step %}
### Join

In Rust press **F1** and type:

```
client.connect YOUR_SERVER_IP:28015
```

Replace the IP and port with the ones shown on the **Console** page of your server.
{% endstep %}
{% endstepper %}

## Ports

| Port | Protocol | Use |
|---|---|---|
| `28015` | UDP | Game connection |
| `28016` | TCP | RCON (remote console) |
| `28082` | TCP | Rust+ companion app |

Your assigned ports are always visible in the panel and may differ from these defaults.

## Plugins (Oxide/uMod)

Install Oxide from the **Startup** tab (or upload it through the **Files** tab), then put plugin `.cs` files into `oxide/plugins` and they load automatically.

{% hint style="info" %}
After a Rust forced wipe (first Thursday of each month) update the server before starting it, otherwise players cannot connect.
{% endhint %}
