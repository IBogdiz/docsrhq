---
description: "Run a Node.js application or Discord bot on RHQ App Hosting."
icon: node-js
---

# Node.js hosting

Your Node.js app runs on our hosting panel (Pterodactyl). It is meant for Discord bots, APIs and small web apps.

{% stepper %}
{% step %}
### Upload your project

Open the **Files** tab and upload your project: `package.json`, your source files and everything else the app needs. Do not upload `node_modules`.
{% endstep %}

{% step %}
### Set the main file

Open the **Startup** tab and set the main file to the one that starts your app, for example `index.js`.
{% endstep %}

{% step %}
### Add your secrets

Put tokens and keys in a `.env` file or in the environment variables offered in **Startup**. Never write them into your code.
{% endstep %}

{% step %}
### Start the app

Press **Start**. Dependencies from `package.json` are installed on start, so the first start takes longer. Watch the **Console** for errors.
{% endstep %}
{% endstepper %}

## Web apps and APIs

If your app listens for HTTP, use the port assigned to your server (shown in the panel). Pterodactyl also exposes it as the `SERVER_PORT` environment variable:

```js
const port = process.env.SERVER_PORT || 3000;
```

## Updating

Upload the changed files, then press **Restart**. If you added packages, update `package.json` so they install on the next start.

{% hint style="info" %}
Need a domain for your app? See [Cloudflare + your domain](../domains-web/cloudflare-domain.md).
{% endhint %}
