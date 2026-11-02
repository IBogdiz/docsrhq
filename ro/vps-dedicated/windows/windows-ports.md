---
description: "Deschide porturi TCP și UDP în firewallul Windows al VPS-ului sau serverului dedicat."
icon: network-wired
---

# Deschiderea porturilor pe Windows

Folosește aceste comenzi ca să deschizi un port în firewallul Windows al serverului tău.

{% stepper %}
{% step %}
### Deschide Command Prompt ca Administrator

Apasă simultan tasta **Windows** și **S**, scrie **CMD** și rulează-l ca **Administrator**.
{% endstep %}

{% step %}
### Deschide portul

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

## Porturi pentru jocuri populare

| Joc | Port | Protocol |
|---|---|---|
| FiveM | `30120` | TCP și UDP |
| Minecraft | `25565` | TCP și UDP |
| Rust | `28015` | TCP și UDP |

## Ghid video

Poți urmări clipul de mai jos pentru mai multe detalii.

{% embed url="https://www.youtube.com/watch?v=rkhTPOG015c" %}

{% hint style="info" %}
Dacă serviciul tău are și firewallul de rețea RHQ, portul trebuie permis și acolo. Vezi [Firewall](../network/firewall.md).
{% endhint %}
