---
description: "Run a Python application or Discord bot on RHQ App Hosting."
icon: python
---

# Python hosting

Your Python app runs on our hosting panel (Pterodactyl). It is meant for Discord bots, scripts and small web apps.

{% stepper %}
{% step %}
### Upload your project

Open the **Files** tab and upload your project: your `.py` files and a `requirements.txt` listing the libraries it needs.
{% endstep %}

{% step %}
### Set the main file

Open the **Startup** tab and set the main file to the one that starts your app, for example `main.py`.
{% endstep %}

{% step %}
### Add your secrets

Put tokens and keys in a `.env` file or in the environment variables offered in **Startup**. Never write them into your code.
{% endstep %}

{% step %}
### Start the app

Press **Start**. Libraries from `requirements.txt` are installed on start, so the first start takes longer. Watch the **Console** for errors.
{% endstep %}
{% endstepper %}

## Web apps and APIs

If your app listens for HTTP, use the port assigned to your server (shown in the panel). Pterodactyl also exposes it as the `SERVER_PORT` environment variable:

```python
import os
port = int(os.environ.get("SERVER_PORT", 8000))
```

## Updating

Upload the changed files, then press **Restart**. If you added libraries, add them to `requirements.txt` so they install on the next start.

{% hint style="info" %}
Need a domain for your app? See [Cloudflare + your domain](../domains-web/cloudflare-domain.md).
{% endhint %}
