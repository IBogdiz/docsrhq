---
description: "Instalează un server de joc pe VPS-ul Linux cu o singură comandă și administrează-l cu RHQ Server Manager."
icon: download
---

# RHQ Game Installer

RHQ Game Installer instalează un server de joc pe VPS-ul tău cu o singură comandă și îți oferă un panou în terminal, **RHQ Server Manager**, ca să îl administrezi.

## Instalare

Conectează-te la VPS prin SSH folosind contul `root`, apoi rulează:

```bash
curl -fsSL https://cdn.rhqnetwork.biz/install | sudo bash
```

Selectează jocul pe care vrei să îl instalezi și apasă `Enter`.

{% hint style="info" %}
Pentru o instalare nouă, recomandăm folosirea unui VPS fresh.
{% endhint %}

## Jocuri suportate

* FiveM
* RedM
* Minecraft (Paper)
* Rust
* Counter-Strike 2
* Palworld
* Valheim
* Terraria (TShock)

## Sisteme suportate

* Debian 12
* Debian 13
* Ubuntu 22.04 LTS
* Ubuntu 24.04 LTS
* AMD64 / x86_64

## RHQ Server Manager

După instalare, serverul poate fi administrat direct prin SSH folosind **RHQ Server Manager**. Din panou poți:

* vedea utilizarea CPU, RAM și a spațiului de stocare
* verifica statusul serverului
* porni, opri și reporni serverul
* vedea logurile
* actualiza serverul
* crea backup-uri
* accesa terminalul Linux

Navigare:

| Tastă | Acțiune |
|---|---|
| ↑ / ↓ | Navigare prin meniu |
| Enter | Selectează o opțiune |
| PgUp / PgDn | Scroll prin loguri |
| H | Revine la Overview |
| Q | Ieșire |

## Update-uri

RHQ Game Installer folosește două sisteme separate de actualizare.

### Update-ul serverului de joc

Actualizează serverul de joc propriu-zis, în funcție de joc:

| Joc | Sursa update-ului |
|---|---|
| FiveM / RedM | Cfx.re Artifacts |
| Minecraft | Paper |
| Rust, Counter-Strike 2, Palworld, Valheim | SteamCMD |
| Terraria | TShock |

### Update automat al panoului RHQ

RHQ Server Manager verifică automat RHQ CDN pentru versiuni noi. Update-urile panelului pot include bug fixes, îmbunătățiri, funcții noi și modificări ale interfeței.

Update-ul panelului RHQ este separat de update-ul serverului de joc. Fișierele tale precum `worlds`, `plugins`, `mods`, `resources`, `maps` și configurațiile serverului nu sunt înlocuite de update-ul panelului.

Panelul verifică în mod normal update-urile aproximativ o dată pe oră. Poți vedea timer-ele RHQ cu:

```bash
systemctl list-timers | grep rhq
```
