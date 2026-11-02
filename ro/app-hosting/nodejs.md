---
description: "Rulează o aplicație Node.js sau un bot de Discord la RHQ App Hosting."
icon: node-js
---

# Hosting Node.js

Aplicația ta Node.js rulează pe panoul nostru de hosting (Pterodactyl). Este făcut pentru boți de Discord, API-uri și aplicații web mici.

{% stepper %}
{% step %}
### Încarcă proiectul

Deschide tabul **Files** și încarcă proiectul: `package.json`, fișierele sursă și tot ce mai are nevoie aplicația. Nu încărca `node_modules`.
{% endstep %}

{% step %}
### Setează fișierul principal

Deschide tabul **Startup** și setează fișierul principal la cel care pornește aplicația, de exemplu `index.js`.
{% endstep %}

{% step %}
### Adaugă secretele

Pune tokenurile și cheile într-un fișier `.env` sau în variabilele de mediu oferite în **Startup**. Nu le scrie niciodată direct în cod.
{% endstep %}

{% step %}
### Pornește aplicația

Apasă **Start**. Dependențele din `package.json` se instalează la pornire, deci prima pornire durează mai mult. Urmărește **Console** pentru erori.
{% endstep %}
{% endstepper %}

## Aplicații web și API-uri

Dacă aplicația ascultă pe HTTP, folosește portul alocat serverului tău (afișat în panou). Pterodactyl îl expune și ca variabilă de mediu `SERVER_PORT`:

```js
const port = process.env.SERVER_PORT || 3000;
```

## Actualizare

Încarcă fișierele modificate, apoi apasă **Restart**. Dacă ai adăugat pachete, actualizează `package.json` ca să se instaleze la următoarea pornire.

{% hint style="info" %}
Ai nevoie de un domeniu pentru aplicație? Vezi [Cloudflare + domeniul tău](../domains-web/cloudflare-domain.md).
{% endhint %}
