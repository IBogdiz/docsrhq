---
description: "Manage the firewall of your VPS, bare metal or colocation service from the client area."
icon: fire-flame-curved
---

# Firewall

If you have a **VPS**, **bare metal** or **colocation** service with RHQ, you can manage its network firewall directly from the client area, without opening a ticket. Filters are applied before traffic reaches your server, so blocked packets never use your bandwidth or CPU.

{% hint style="info" %}
The firewall is available only for VPS, bare metal and colocation services.
{% endhint %}

## Open the firewall

{% stepper %}
{% step %}
### Log in to the client area

Open your RHQ client area and go to **Services**.
{% endstep %}

{% step %}
### Select the service

Click the VPS, bare metal or colocation service you want to protect.
{% endstep %}

{% step %}
### Open the Firewall section

In the service page open **Firewall**. You will see the list of rules currently applied to the IP address of the service.
{% endstep %}
{% endstepper %}

## Add a rule

Every rule is made of the same few fields:

| Field | Meaning |
|---|---|
| Action | **Allow** or **Block** matching traffic |
| Protocol | TCP, UDP or ICMP |
| Port | A single port (`22`) or a range (`27015-27030`) |
| Source | An IP or network (`1.2.3.4`, `10.0.0.0/24`) or any address |

Rules are evaluated from top to bottom and the first match wins, so put specific rules above general ones.

## Common examples

{% tabs %}
{% tab title="Restrict SSH" %}
Allow TCP port `22` only from your own IP, then block TCP port `22` from any other source.
{% endtab %}

{% tab title="Game server" %}
Allow the game's port (for example UDP `28015` for Rust) from any source and block everything else you do not use.
{% endtab %}

{% tab title="Web server" %}
Allow TCP ports `80` and `443` from any source. If you use Cloudflare, allow them only from [Cloudflare's IP ranges](https://www.cloudflare.com/ips/).
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
Before blocking SSH or RDP, make sure a rule allowing **your** IP is above it. A wrong rule can lock you out of your own server. If that happens, remove the rule from the client area or open a ticket.
{% endhint %}

## Tips

* Open only the ports you actually use.
* Do not forget that your home IP can change; keep a console or VNC option available.
* Under attack, add a block rule for the offending source or protocol first and then look at the traffic with a [.pcap capture](wireshark-pcap.md).
