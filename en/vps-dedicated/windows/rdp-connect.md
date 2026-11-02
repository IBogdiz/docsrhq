---
description: "Connect to your Windows VPS or dedicated server with Remote Desktop (RDP)."
icon: desktop
---

# Connect with RDP

Follow the steps below to connect to your VPS or dedicated server running Windows.

{% stepper %}
{% step %}
### Open Remote Desktop Connection

The application is already installed on your PC. Search for **Remote Desktop Connection** in the Start menu.

<figure><img src="../../.gitbook/assets/rdp-01-open-app.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Enter the VPS IP

Fill in the empty field with the IP address of your VPS.

<figure><img src="../../.gitbook/assets/rdp-02-enter-ip.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Authenticate

* **Username:** `Administrator`
* **Password:** the one shown in your client area at [my.rhqhosting.com](https://my.rhqhosting.com).

<figure><img src="../../.gitbook/assets/rdp-03-credentials.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Confirm the connection

After authenticating, click **Yes** in the window that appears.

<figure><img src="../../.gitbook/assets/rdp-04-confirm.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

{% hint style="info" %}
Cannot connect? Make sure TCP port `3389` is allowed in your [firewall](../network/firewall.md). To change the password afterwards, see [Change your Windows password](password-reset.md).
{% endhint %}
