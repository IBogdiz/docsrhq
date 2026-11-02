---
description: "How the RHQ game panel works: console, files, startup settings and the guides for each game."
icon: gamepad-modern
---

# Game hosting overview

All RHQ game servers run on our game panel (Pterodactyl). The panel looks the same for every game, so once you know it you can manage any server.

## The panel at a glance

| Tab | What it is for |
|---|---|
| **Console** | Start, stop and restart the server, read the live log and type commands |
| **Files** | Browse, edit and upload server files such as configs, plugins and mods |
| **Startup** | Server name, game version, license keys and other launch settings |
| **Network** | The IP address and ports assigned to your server |

{% hint style="info" %}
Always **stop** the server before editing important files. Some games overwrite their config when they shut down.
{% endhint %}

## Guides by game

<table data-view="cards"><thead><tr><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>Rust</strong></td><td><a href="rust.md">rust.md</a></td></tr><tr><td><strong>RedM</strong></td><td><a href="redm.md">redm.md</a></td></tr><tr><td><strong>Euro Truck Simulator 2</strong></td><td><a href="euro-truck-simulator-2.md">euro-truck-simulator-2.md</a></td></tr></tbody></table>

## Related guides

* [Firewall](../servers-network/firewall.md): control who can reach your server.
* [Cloudflare + your domain](../domains-web/cloudflare-domain.md): use a custom address such as `play.yourdomain.com`.
