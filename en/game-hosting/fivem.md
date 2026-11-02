---
description: "Create and configure a FiveM (GTA V) server on RHQ Game Hosting."
icon: gamepad
---

# FiveM server

FiveM is the multiplayer modification for GTA V. Your server runs on our game panel (Pterodactyl).

{% stepper %}
{% step %}
### Get a license key

Create a free key at [portal.cfx.re](https://portal.cfx.re) under **Server → Registration keys** and copy it.
{% endstep %}

{% step %}
### Enter the key in the panel

Open your server in the game panel, go to **Startup** and paste the key in the license field.
{% endstep %}

{% step %}
### Start the server

Press **Start** and wait for the console to finish loading. The first start downloads the server artifacts.
{% endstep %}

{% step %}
### Configure it

In the **Files** tab edit `server.cfg`: set `sv_hostname`, `sv_maxclients` and the resources you want to start with `ensure resource_name`.
{% endstep %}

{% step %}
### Join

Open FiveM, press **F8** and type:

```
connect YOUR_SERVER_IP:30120
```
{% endstep %}
{% endstepper %}

## Ports

| Port | Protocol | Use |
|---|---|---|
| `30120` | TCP and UDP | Game connection |

Your assigned ports are always visible in the panel and may differ from these defaults.

## Adding resources

Upload the resource folder to `resources/` in the **Files** tab, add `ensure folder_name` to `server.cfg` and restart.

{% hint style="info" %}
Prefer to run FiveM on your own VPS? See [FXServer on Windows](fxserver-windows.md) or [FXServer on Linux](fxserver-linux.md).
{% endhint %}

{% hint style="warning" %}
Only install resources from sources you trust. A malicious resource can run code on your server.
{% endhint %}
