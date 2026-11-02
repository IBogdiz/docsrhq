---
description: "Create and configure a RedM (Red Dead Redemption 2) server on RHQ Game Hosting."
icon: hat-cowboy
---

# RedM server

RedM is the multiplayer modification for Red Dead Redemption 2, built on the same technology as FiveM. Your server runs on our game panel (Pterodactyl).

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

Open RedM, press **F8** and type:

```
connect YOUR_SERVER_IP:30120
```
{% endstep %}
{% endstepper %}

## Ports

| Port | Protocol | Use |
|---|---|---|
| `30120` | TCP and UDP | Game connection |

## Adding resources

Upload the resource folder to `resources/` in the **Files** tab, add `ensure folder_name` to `server.cfg` and restart.

{% hint style="warning" %}
Only install resources from sources you trust. A malicious resource can run code on your server.
{% endhint %}
