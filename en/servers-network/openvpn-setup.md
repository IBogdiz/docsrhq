---
description: "Install an OpenVPN server on your VPS and connect to it from your devices."
icon: shield-halved
---

# OpenVPN setup

This guide shows how to turn your VPS into a personal VPN server with OpenVPN, then connect to it from your PC or phone.

{% hint style="info" %}
**Requirements:** a VPS running Debian, Ubuntu, AlmaLinux or Rocky Linux, root access over SSH, and a TUN/TAP-enabled virtualization (KVM works out of the box).
{% endhint %}

{% stepper %}
{% step %}
### Connect to your VPS

```bash
ssh root@YOUR_VPS_IP
```
{% endstep %}

{% step %}
### Download the installer

```bash
curl -O https://raw.githubusercontent.com/angristan/openvpn-install/master/openvpn-install.sh
chmod +x openvpn-install.sh
```
{% endstep %}

{% step %}
### Run it and answer the questions

```bash
./openvpn-install.sh
```

The defaults are fine for most users: UDP, port `1194`, and the DNS provider of your choice. When asked for a client name, enter something like `laptop` or `phone`.
{% endstep %}

{% step %}
### Open the port in your firewall

If you use a firewall on the VPS or in the RHQ client area, allow **UDP 1194** (or the port you chose).

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
### Download the client profile

The script creates a file like `/root/laptop.ovpn`. Copy it to your computer:

```bash
scp root@YOUR_VPS_IP:/root/laptop.ovpn .
```
{% endstep %}

{% step %}
### Connect

Install **OpenVPN Connect** (Windows, macOS, Android, iOS), import the `.ovpn` file and press connect. Your public IP should now be the IP of your VPS.
{% endstep %}
{% endstepper %}

## Add or remove clients

Run the script again and choose the matching option from the menu:

```bash
./openvpn-install.sh
```

{% hint style="warning" %}
Never share a `.ovpn` file. It contains the keys needed to use your VPN. Create one profile per device and revoke it if the device is lost.
{% endhint %}

## Troubleshooting

<details>

<summary>It connects but there is no internet</summary>

Check that IP forwarding is enabled (`sysctl net.ipv4.ip_forward` should return `1`) and that the NAT rule created by the script is still present (`iptables -t nat -L -n`).

</details>

<details>

<summary>The connection times out</summary>

The port is almost certainly blocked. Confirm the OpenVPN service is running with `systemctl status openvpn*` and that UDP 1194 is open in every firewall between you and the VPS.

</details>
