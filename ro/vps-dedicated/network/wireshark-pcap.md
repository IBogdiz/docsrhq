---
description: "Capturează traficul serverului cu tcpdump și analizează fișierul .pcap în Wireshark."
icon: magnifying-glass-chart
---

# Analiză Wireshark (.pcap)

Un fișier `.pcap` este o înregistrare a pachetelor de rețea. Este cea mai rapidă metodă să înțelegi un atac, o conexiune lentă sau un serviciu care nu se conectează. Ghidul arată cum înregistrezi un `.pcap` pe server și cum îl citești în Wireshark.

{% stepper %}
{% step %}
### Capturează pe server

Instalează `tcpdump` dacă lipsește, apoi înregistrează într-un fișier. Înlocuiește `eth0` cu interfața ta de rețea (o vezi cu `ip a`).

```bash
apt install tcpdump -y        # Debian / Ubuntu
tcpdump -i eth0 -c 50000 -w capture.pcap
```

`-c 50000` oprește captura după 50.000 de pachete ca fișierul să rămână mic. Ca să înregistrezi doar un port:

```bash
tcpdump -i eth0 -c 50000 -w capture.pcap port 25565
```
{% endstep %}

{% step %}
### Descarcă fișierul

```bash
scp root@IP_SERVER:capture.pcap .
```
{% endstep %}

{% step %}
### Deschide-l în Wireshark

Instalează [Wireshark](https://www.wireshark.org/download.html) pe calculator și deschide `capture.pcap` cu **File → Open**.
{% endstep %}

{% step %}
### Găsește ce cauți

Scrie un filtru de afișare în bara de sus și apasă Enter.
{% endstep %}
{% endstepper %}

## Filtre utile

| Scop | Filtru |
|---|---|
| Trafic de la o adresă IP | `ip.src == 1.2.3.4` |
| Trafic către sau de la o adresă IP | `ip.addr == 1.2.3.4` |
| Un port | `tcp.port == 80` sau `udp.port == 27015` |
| Doar pachete SYN (floduri) | `tcp.flags.syn == 1 && tcp.flags.ack == 0` |
| Doar DNS | `dns` |
| Retransmisii (conexiune slabă) | `tcp.analysis.retransmission` |

## Cum recunoști un atac

Deschide **Statistics → Conversations** și sortează după **Packets**. Câteva adrese cu un număr uriaș de pachete, sau mii de adrese care trimit câte un pachet, înseamnă de obicei un flood. **Statistics → Protocol Hierarchy** arată ce protocol domină traficul.

{% hint style="info" %}
Dacă deschizi un tichet despre un atac, atașează `.pcap`-ul (sau primele câteva mii de pachete). Echipa noastră poate scrie mult mai repede un filtru precis.
{% endhint %}

{% hint style="warning" %}
O captură poate conține date private, de exemplu parole necriptate sau cookieuri de sesiune. Nu o publica.
{% endhint %}
