---
description: "Install Node.js on Linux with NVM (Node Version Manager)."
icon: node-js
---

# Install Node.js

To install Node.js on Linux we recommend NVM (Node Version Manager), which lets you install and switch between several Node.js versions.

## Install NVM

```bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

After the installation, reconnect to SSH or run:

```bash
. ~/.bashrc
```

NVM is now available through the `nvm` command.

## Useful commands

{% tabs %}
{% tab title="Check versions" %}
View the installed Node.js versions:

```bash
nvm list
```

Check which version is currently in use:

```bash
nvm current
```

```bash
nvm version
```
{% endtab %}

{% tab title="Install" %}
Install the version you want:

```bash
nvm install <nodejs_version>
```
{% endtab %}

{% tab title="Switch" %}
Switch version (only useful if several versions are installed):

```bash
nvm use <nodejs_version>
```

Set a default version:

```bash
nvm alias default <nodejs_version>
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
The commands accept major versions such as `16`, `18` or `20`. You do not need to write the full `xx.xx.xx` format.
{% endhint %}
