---
description: "Capture traffic on your server with tcpdump and analyze the .pcap file in Wireshark."
icon: magnifying-glass-chart
---

# Wireshark (.pcap) analysis

A `.pcap` file is a recording of network packets. It is the fastest way to understand an attack, a slow connection or a service that will not connect. This guide shows how to record one on your server and read it in Wireshark.

{% stepper %}
{% step %}
### Capture on the server

Install `tcpdump` if it is missing, then record to a file. Replace `eth0` with your network interface (check with `ip a`).

```bash
apt install tcpdump -y        # Debian / Ubuntu
tcpdump -i eth0 -c 50000 -w capture.pcap
```

`-c 50000` stops after 50,000 packets so the file stays small. To record only one port:

```bash
tcpdump -i eth0 -c 50000 -w capture.pcap port 25565
```
{% endstep %}

{% step %}
### Download the file

```bash
scp root@YOUR_SERVER_IP:capture.pcap .
```
{% endstep %}

{% step %}
### Open it in Wireshark

Install [Wireshark](https://www.wireshark.org/download.html) on your computer and open `capture.pcap` with **File → Open**.
{% endstep %}

{% step %}
### Find what you are looking for

Type a display filter in the bar at the top and press Enter.
{% endstep %}
{% endstepper %}

## Useful display filters

| Goal | Filter |
|---|---|
| Traffic from one IP | `ip.src == 1.2.3.4` |
| Traffic to or from one IP | `ip.addr == 1.2.3.4` |
| One port | `tcp.port == 80` or `udp.port == 27015` |
| Only SYN packets (floods) | `tcp.flags.syn == 1 && tcp.flags.ack == 0` |
| DNS only | `dns` |
| Retransmissions (bad connection) | `tcp.analysis.retransmission` |

## Spotting an attack

Open **Statistics → Conversations** and sort by **Packets**. A handful of addresses with a huge packet count, or thousands of addresses sending one packet each, usually means a flood. **Statistics → Protocol Hierarchy** shows which protocol dominates the traffic.

{% hint style="info" %}
If you open a ticket about an attack, attach the `.pcap` (or its first few thousand packets). It lets our team write a precise filter much faster.
{% endhint %}

{% hint style="warning" %}
A capture can contain private data such as unencrypted passwords or session cookies. Do not share it publicly.
{% endhint %}
