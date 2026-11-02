---
description: "Install a FiveM FXServer on Linux step by step."
icon: linux
---

# FXServer on Linux

This guide installs a FiveM server (FXServer) on a Linux VPS or dedicated server.

## Requirements

* **Git**, if you want to follow the recommended way of cloning the main server data.
* **The `xz` or `xz-utils` package.** On most Linux systems it is pre-installed.

## Installation

{% stepper %}
{% step %}
### Create the server folder

Create a new folder for the server binaries:

```bash
mkdir -p ~/FXServer/server
```
{% endstep %}

{% step %}
### Download the server build

Download the current recommended version of the master branch for Linux from the Linux server build list. Copy the URL of the recommended version and download it with `wget` (save it as `fx.tar.xz`).
{% endstep %}

{% step %}
### Extract the archive

```bash
cd ~/FXServer/server && tar xf fx.tar.xz
```

You need `xz` installed. On Debian/Ubuntu it is in the `xz-utils` package.
{% endstep %}

{% step %}
### Clone the server data

Clone `cfx-server-data` into a new folder outside the server binaries folder:

```bash
git clone https://github.com/citizenfx/cfx-server-data.git ~/FXServer/server-data
```
{% endstep %}

{% step %}
### Create server.cfg

Create a `server.cfg` file in the `server-data` folder and fill it with the example configuration from the Cfx.re documentation.
{% endstep %}

{% step %}
### Set the license key

Set your license key in `server.cfg`:

```
sv_licenseKey "licenseKeyGoesHere"
```

You can create a key at [portal.cfx.re](https://portal.cfx.re).
{% endstep %}

{% step %}
### Run the server

Run the server from the `server-data` folder:

```bash
cd ~/FXServer/server-data && bash ~/FXServer/server/run.sh +exec server.cfg
```
{% endstep %}
{% endstepper %}

{% hint style="info" %}
Prefer a faster setup? The [RHQ Game Installer](../vps-dedicated/linux/rhq-game-installer.md) installs FiveM with one command.
{% endhint %}
