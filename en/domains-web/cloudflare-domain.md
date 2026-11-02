---
description: "Add your domain to Cloudflare and point it to your RHQ server."
icon: cloud
---

# Cloudflare + your domain

Cloudflare gives you free DNS, a CDN and basic DDoS protection for websites. This guide connects your domain to Cloudflare and then to your RHQ service.

{% hint style="info" %}
You need a domain you own (from any registrar) and the IP address of your RHQ server, which you can find in the client area.
{% endhint %}

{% stepper %}
{% step %}
### Add the site to Cloudflare

Create a free account at [cloudflare.com](https://www.cloudflare.com), click **Add a domain**, enter your domain and choose the **Free** plan.
{% endstep %}

{% step %}
### Change the nameservers at your registrar

Cloudflare shows you two nameservers (for example `name.ns.cloudflare.com`). Log in at the registrar where you bought the domain, replace the existing nameservers with these two and save.

Propagation usually takes from a few minutes up to 24 hours. Cloudflare emails you when the domain is active.
{% endstep %}

{% step %}
### Point the domain to your server

In Cloudflare open **DNS → Records** and add:

| Type | Name | Content | Proxy status |
|---|---|---|---|
| A | `@` | `YOUR_SERVER_IP` | Proxied (orange cloud) |
| CNAME | `www` | `yourdomain.com` | Proxied (orange cloud) |
{% endstep %}

{% step %}
### Set SSL/TLS mode

Go to **SSL/TLS → Overview** and choose **Full (strict)** if your server has a valid certificate (for example Let's Encrypt). Use **Full** if it has a self-signed one. Avoid **Flexible**: it causes redirect loops on most sites.
{% endstep %}
{% endstepper %}

## When to disable the proxy

The orange cloud only works for HTTP and HTTPS traffic. For game servers, mail, SSH or anything else, set the record to **DNS only** (grey cloud), otherwise the connection will fail.

{% tabs %}
{% tab title="Website" %}
Proxied (orange cloud) is recommended.
{% endtab %}

{% tab title="Game server" %}
Use **DNS only** and point an `A` record such as `play` to the server IP.
{% endtab %}

{% tab title="Mail" %}
Use **DNS only** for the `mail` record and for any `MX` target.
{% endtab %}
{% endtabs %}

## Troubleshooting

<details>

<summary>The site shows error 521 or 522</summary>

Cloudflare cannot reach your server. Check that the web server is running and that your firewall allows Cloudflare's IP ranges on ports 80 and 443.

</details>

<details>

<summary>The domain still shows the old site</summary>

DNS has not finished propagating or your browser cached the old address. Wait a little and test with `nslookup yourdomain.com`.

</details>
