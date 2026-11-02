---
description: "Install a game server on your Linux VPS with one command and manage it with RHQ Server Manager."
icon: download
---

# RHQ Game Installer

The RHQ Game Installer sets up a game server on your VPS with one command and gives you a terminal panel, **RHQ Server Manager**, to run it.

## Installation

Connect to your VPS through SSH using the `root` account, then run:

```bash
curl -fsSL https://cdn.rhqnetwork.biz/install | sudo bash
```

Select the game you want to install and press `Enter`.

{% hint style="info" %}
For a new installation, we recommend using a fresh VPS.
{% endhint %}

## Supported games

* FiveM
* RedM
* Minecraft (Paper)
* Rust
* Counter-Strike 2
* Palworld
* Valheim
* Terraria (TShock)

## Supported systems

* Debian 12
* Debian 13
* Ubuntu 22.04 LTS
* Ubuntu 24.04 LTS
* AMD64 / x86_64

## RHQ Server Manager

After installation, the server can be managed directly through SSH using **RHQ Server Manager**. From the panel you can:

* view CPU, RAM and disk usage
* check the server status
* start, stop and restart the server
* view logs
* update the server
* create backups
* access the Linux shell

Navigation:

| Key | Action |
|---|---|
| ↑ / ↓ | Navigate through the menu |
| Enter | Select an option |
| PgUp / PgDn | Scroll through logs |
| H | Return to Overview |
| Q | Exit |

## Updates

RHQ Game Installer uses two separate update systems.

### Game server update

Updates the actual game server, depending on the game:

| Game | Update source |
|---|---|
| FiveM / RedM | Cfx.re Artifacts |
| Minecraft | Paper |
| Rust, Counter-Strike 2, Palworld, Valheim | SteamCMD |
| Terraria | TShock |

### RHQ Panel auto update

RHQ Server Manager automatically checks the RHQ CDN for new versions. Panel updates can include bug fixes, improvements, new features and interface changes.

RHQ Panel updates are separate from game server updates. Your `worlds`, `plugins`, `mods`, `resources`, `maps` and server configuration are not replaced by panel updates.

The panel normally checks for updates about once every hour. You can see the RHQ timers with:

```bash
systemctl list-timers | grep rhq
```
