---
description: "Rulează o aplicație Python sau un bot de Discord la RHQ App Hosting."
icon: python
---

# Hosting Python

Aplicația ta Python rulează pe panoul nostru de hosting (Pterodactyl). Este făcut pentru boți de Discord, scripturi și aplicații web mici.

{% stepper %}
{% step %}
### Încarcă proiectul

Deschide tabul **Files** și încarcă proiectul: fișierele `.py` și un `requirements.txt` cu bibliotecile de care are nevoie.
{% endstep %}

{% step %}
### Setează fișierul principal

Deschide tabul **Startup** și setează fișierul principal la cel care pornește aplicația, de exemplu `main.py`.
{% endstep %}

{% step %}
### Adaugă secretele

Pune tokenurile și cheile într-un fișier `.env` sau în variabilele de mediu oferite în **Startup**. Nu le scrie niciodată direct în cod.
{% endstep %}

{% step %}
### Pornește aplicația

Apasă **Start**. Bibliotecile din `requirements.txt` se instalează la pornire, deci prima pornire durează mai mult. Urmărește **Console** pentru erori.
{% endstep %}
{% endstepper %}

## Aplicații web și API-uri

Dacă aplicația ascultă pe HTTP, folosește portul alocat serverului tău (afișat în panou). Pterodactyl îl expune și ca variabilă de mediu `SERVER_PORT`:

```python
import os
port = int(os.environ.get("SERVER_PORT", 8000))
```

## Actualizare

Încarcă fișierele modificate, apoi apasă **Restart**. Dacă ai adăugat biblioteci, adaugă-le în `requirements.txt` ca să se instaleze la următoarea pornire.

{% hint style="info" %}
Ai nevoie de un domeniu pentru aplicație? Vezi [Cloudflare + domeniul tău](../domains-web/cloudflare-domain.md).
{% endhint %}
