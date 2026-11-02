---
description: "Conectează-te la VPS-ul sau serverul dedicat cu Windows prin Remote Desktop (RDP)."
icon: desktop
---

# Conectare prin RDP

Urmează pașii de mai jos ca să te conectezi la VPS-ul sau serverul dedicat care rulează Windows.

{% stepper %}
{% step %}
### Deschide Remote Desktop Connection

Aplicația vine deja instalată pe PC. Caută **Remote Desktop Connection** în meniul Start.

<figure><img src="../../.gitbook/assets/rdp-01-open-app.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Introdu IP-ul VPS-ului

Completează câmpul gol cu adresa IP a VPS-ului.

<figure><img src="../../.gitbook/assets/rdp-02-enter-ip.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Autentifică-te

* **Nume utilizator:** `Administrator`
* **Parolă:** cea afișată în zona ta de client, la [my.rhqhosting.com](https://my.rhqhosting.com).

<figure><img src="../../.gitbook/assets/rdp-03-credentials.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Confirmă conexiunea

După autentificare, apasă **Yes** în fereastra care apare.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
Nu te poți conecta? Verifică dacă portul TCP `3389` este permis în [firewall](../network/firewall.md). Ca să schimbi parola după aceea, vezi [Schimbarea parolei Windows](password-reset.md).
{% endhint %}
