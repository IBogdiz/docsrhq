---
description: "Open TCP and UDP ports in the Windows firewall of your VPS or dedicated server."
icon: network-wired
---

# Open ports on Windows

Use these commands to open a port in the Windows firewall of your server.

{% stepper %}
{% step %}
### Open Command Prompt as Administrator

Press the **Windows** key and **S** at the same time, type **CMD** and run it as **Administrator**.
{% endstep %}

{% step %}
### Open the port

{% tabs %}
{% tab title="TCP" %}
```
netsh advfirewall firewall add rule name="TCP Port " dir=in action=allow protocol=TCP localport=[replace_with_port_number]
```
{% endtab %}

{% tab title="UDP" %}
```
netsh advfirewall firewall add rule name="UDP Port " dir=in action=allow protocol=UDP localport=[replace_with_port_number]
```
{% endtab %}
{% endtabs %}
{% endstep %}
{% endstepper %}

## Ports for popular games

| Game | Port | Protocol |
|---|---|---|
| FiveM | `30120` | TCP and UDP |
| Minecraft | `25565` | TCP and UDP |
| Rust | `28015` | TCP and UDP |

## Video guide

You can watch the clip below for more details.

{% embed url="https://www.youtube.com/watch?v=rkhTPOG015c" %}

{% hint style="info" %}
If your service also has the RHQ network firewall, the port must be allowed there too. See [Firewall](../network/firewall.md).
{% endhint %}
