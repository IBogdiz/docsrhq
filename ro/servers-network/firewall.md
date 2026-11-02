---
description: "Administrează firewallul serviciului tău VPS, server dedicat sau colocare din zona de client."
icon: fire-flame-curved
---

# Firewall

Dacă ai un serviciu **VPS**, **server dedicat** sau **colocare** la RHQ, poți administra firewallul de rețea direct din zona de client, fără să deschizi tichet. Filtrele se aplică înainte ca traficul să ajungă la server, deci pachetele blocate nu consumă banda sau procesorul tău.

{% hint style="info" %}
Firewallul este disponibil doar pentru serviciile VPS, server dedicat și colocare.
{% endhint %}

## Deschide firewallul

{% stepper %}
{% step %}
### Autentifică-te în zona de client

Deschide zona de client RHQ și intră la **Services**.
{% endstep %}

{% step %}
### Alege serviciul

Dă click pe VPS-ul, serverul dedicat sau serviciul de colocare pe care vrei să îl protejezi.
{% endstep %}

{% step %}
### Deschide secțiunea Firewall

În pagina serviciului deschide **Firewall**. Vei vedea lista regulilor aplicate pe adresa IP a serviciului.
{% endstep %}
{% endstepper %}

## Adaugă o regulă

Fiecare regulă are aceleași câmpuri:

| Câmp | Ce înseamnă |
|---|---|
| Acțiune | **Allow** (permite) sau **Block** (blochează) traficul care se potrivește |
| Protocol | TCP, UDP sau ICMP |
| Port | Un singur port (`22`) sau un interval (`27015-27030`) |
| Sursă | O adresă IP sau rețea (`1.2.3.4`, `10.0.0.0/24`) sau orice adresă |

Regulile se evaluează de sus în jos și prima potrivire câștigă, deci pune regulile specifice deasupra celor generale.

## Exemple frecvente

{% tabs %}
{% tab title="Restricționează SSH" %}
Permite portul TCP `22` doar de la IP-ul tău, apoi blochează portul TCP `22` de la orice altă sursă.
{% endtab %}

{% tab title="Server de jocuri" %}
Permite portul jocului (de exemplu UDP `28015` pentru Rust) de la orice sursă și blochează tot ce nu folosești.
{% endtab %}

{% tab title="Server web" %}
Permite porturile TCP `80` și `443` de la orice sursă. Dacă folosești Cloudflare, permite-le doar din [intervalele IP Cloudflare](https://www.cloudflare.com/ips/).
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
Înainte să blochezi SSH sau RDP, asigură-te că există o regulă care permite IP-ul **tău** deasupra. O regulă greșită te poate bloca din propriul server. Dacă se întâmplă, șterge regula din zona de client sau deschide un tichet.
{% endhint %}

## Sfaturi

* Deschide doar porturile pe care le folosești.
* Nu uita că IP-ul de acasă se poate schimba; păstrează la îndemână consola sau VNC.
* Când ești atacat, adaugă mai întâi o regulă de blocare pentru sursa sau protocolul care atacă și apoi uită-te la trafic cu o [captură .pcap](wireshark-pcap.md).
