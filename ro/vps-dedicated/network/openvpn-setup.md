---
description: "Instalează un server OpenVPN pe VPS și conectează-te la el de pe dispozitivele tale."
icon: shield-halved
---

# Configurare OpenVPN

Acest ghid arată cum transformi VPS-ul într-un server VPN personal cu OpenVPN și cum te conectezi la el de pe PC sau telefon.

{% hint style="info" %}
**Ai nevoie de:** un VPS cu Debian, Ubuntu, AlmaLinux sau Rocky Linux, acces root prin SSH și virtualizare cu TUN/TAP activat (KVM funcționează din start).
{% endhint %}

{% stepper %}
{% step %}
### Conectează-te la VPS

```bash
ssh root@IP_VPS
```
{% endstep %}

{% step %}
### Descarcă scriptul de instalare

```bash
curl -O https://raw.githubusercontent.com/angristan/openvpn-install/master/openvpn-install.sh
chmod +x openvpn-install.sh
```
{% endstep %}

{% step %}
### Rulează-l și răspunde la întrebări

```bash
./openvpn-install.sh
```

Valorile implicite merg pentru majoritatea utilizatorilor: UDP, portul `1194` și furnizorul DNS dorit. Când ți se cere numele clientului, scrie ceva de genul `laptop` sau `telefon`.
{% endstep %}

{% step %}
### Deschide portul în firewall

Dacă folosești firewall pe VPS sau în zona de client RHQ, permite **UDP 1194** (sau portul ales de tine).

{% tabs %}
{% tab title="UFW" %}
```bash
ufw allow 1194/udp
```
{% endtab %}

{% tab title="firewalld" %}
```bash
firewall-cmd --permanent --add-port=1194/udp
firewall-cmd --reload
```
{% endtab %}
{% endtabs %}
{% endstep %}

{% step %}
### Descarcă profilul clientului

Scriptul creează un fișier de genul `/root/laptop.ovpn`. Copiază-l pe calculatorul tău:

```bash
scp root@IP_VPS:/root/laptop.ovpn .
```
{% endstep %}

{% step %}
### Conectează-te

Instalează **OpenVPN Connect** (Windows, macOS, Android, iOS), importă fișierul `.ovpn` și apasă conectare. IP-ul tău public ar trebui să fie acum IP-ul VPS-ului.
{% endstep %}
{% endstepper %}

## Adaugă sau șterge clienți

Rulează din nou scriptul și alege opțiunea potrivită din meniu:

```bash
./openvpn-install.sh
```

{% hint style="warning" %}
Nu da nimănui fișierul `.ovpn`. Conține cheile necesare pentru a folosi VPN-ul tău. Creează câte un profil pentru fiecare dispozitiv și revocă-l dacă dispozitivul se pierde.
{% endhint %}

## Depanare

<details>

<summary>Se conectează, dar nu am internet</summary>

Verifică dacă IP forwarding este activ (`sysctl net.ipv4.ip_forward` trebuie să returneze `1`) și dacă regula NAT creată de script există încă (`iptables -t nat -L -n`).

</details>

<details>

<summary>Conexiunea expiră (timeout)</summary>

Cel mai probabil portul este blocat. Confirmă că serviciul OpenVPN rulează cu `systemctl status openvpn*` și că UDP 1194 este deschis în toate firewallurile dintre tine și VPS.

</details>
