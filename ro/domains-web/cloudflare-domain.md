---
description: "Adaugă domeniul tău în Cloudflare și îndreaptă-l spre serverul tău RHQ."
icon: cloud
---

# Cloudflare + domeniul tău

Cloudflare îți oferă DNS gratuit, CDN și protecție de bază împotriva DDoS pentru site-uri. Ghidul conectează domeniul la Cloudflare și apoi la serviciul tău RHQ.

{% hint style="info" %}
Ai nevoie de un domeniu al tău (de la orice registrar) și de adresa IP a serverului RHQ, pe care o găsești în zona de client.
{% endhint %}

{% stepper %}
{% step %}
### Adaugă site-ul în Cloudflare

Creează un cont gratuit la [cloudflare.com](https://www.cloudflare.com), apasă **Add a domain**, introdu domeniul și alege planul **Free**.
{% endstep %}

{% step %}
### Schimbă nameserverele la registrar

Cloudflare îți arată două nameservere (de exemplu `name.ns.cloudflare.com`). Intră în contul de la registrarul unde ai cumpărat domeniul, înlocuiește nameserverele existente cu aceste două și salvează.

Propagarea durează de obicei de la câteva minute până la 24 de ore. Cloudflare îți trimite email când domeniul este activ.
{% endstep %}

{% step %}
### Îndreaptă domeniul spre server

În Cloudflare deschide **DNS → Records** și adaugă:

| Tip | Nume | Conținut | Proxy |
|---|---|---|---|
| A | `@` | `IP_SERVER` | Proxied (nor portocaliu) |
| CNAME | `www` | `domeniultau.ro` | Proxied (nor portocaliu) |
{% endstep %}

{% step %}
### Setează modul SSL/TLS

Intră la **SSL/TLS → Overview** și alege **Full (strict)** dacă serverul are certificat valid (de exemplu Let's Encrypt). Folosește **Full** dacă are certificat autosemnat. Evită **Flexible**: provoacă bucle de redirecționare pe majoritatea site-urilor.
{% endstep %}
{% endstepper %}

## Când dezactivezi proxy-ul

Norul portocaliu funcționează doar pentru trafic HTTP și HTTPS. Pentru servere de jocuri, email, SSH sau orice altceva, setează înregistrarea pe **DNS only** (nor gri), altfel conexiunea nu va merge.

{% tabs %}
{% tab title="Site web" %}
Se recomandă Proxied (nor portocaliu).
{% endtab %}

{% tab title="Server de jocuri" %}
Folosește **DNS only** și îndreaptă o înregistrare `A`, de exemplu `play`, spre IP-ul serverului.
{% endtab %}

{% tab title="Email" %}
Folosește **DNS only** pentru înregistrarea `mail` și pentru orice țintă `MX`.
{% endtab %}
{% endtabs %}

## Depanare

<details>

<summary>Site-ul arată eroarea 521 sau 522</summary>

Cloudflare nu poate ajunge la serverul tău. Verifică dacă serverul web rulează și dacă firewallul permite intervalele IP Cloudflare pe porturile 80 și 443.

</details>

<details>

<summary>Domeniul arată încă site-ul vechi</summary>

DNS-ul nu s-a propagat complet sau browserul a păstrat adresa veche în cache. Așteaptă puțin și testează cu `nslookup domeniultau.ro`.

</details>
