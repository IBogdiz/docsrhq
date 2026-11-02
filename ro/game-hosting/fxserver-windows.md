---
description: "Instalează și pornește un FXServer FiveM pe Windows cu Recipe Deployer de la Cfx.re."
icon: windows
---

# FXServer pe Windows

Acest ghid instalează un server FiveM (FXServer) pe un VPS sau server dedicat cu Windows.

{% hint style="warning" %}
Ai nevoie neapărat de un **cont Cfx.re** ca să legi și să rulezi serverul.
{% endhint %}

{% stepper %}
{% step %}
### Verifică fișierele

Asigură-te că toate fișierele necesare sunt prezente în directorul extras, ca să eviți erorile la pornire. După ce fișierele sunt descărcate și plasate corect, treci la pornirea serverului.

<figure><img src="../.gitbook/assets/fx-00-files.png" alt="" width="520"><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Pornește serverul

Dă dublu clic pe `FXServer.exe` sau pornește-l din CMD/Terminal.

<div align="left"><figure><img src="../.gitbook/assets/fx-01-launch.png" alt="" width="470"><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Leagă contul cu PIN-ul

O pagină ar trebui să se deschidă în browser. Asigură-te că PIN-ul este completat și apasă **Link Account**.

<div align="left"><figure><img src="../.gitbook/assets/fx-02-pin.png" alt="" width="437"><figcaption><p>Codul îl găsești în consola care a pornit odată cu .exe-ul</p></figcaption></figure></div>
{% endstep %}

{% step %}
### Autentifică-te la Cfx.re

Conectează-te la contul tău Cfx.re în această filă, apoi apasă **Continue**.

<div align="left"><figure><img src="../.gitbook/assets/fx-03-login.png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Setează o parolă și acceptă termenii

1. Setează o parolă pentru a te conecta la pagina de administrare a serverului.
2. Acceptă termenii și condițiile.

<div align="left"><figure><img src="../.gitbook/assets/fx-04-password-terms.png" alt="" width="407"><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Dă un nume serverului

Introdu un nume pentru server și apasă **Next**, apoi selectează **Popular Recipes** (Rețete populare).

<div align="left"><figure><img src="../.gitbook/assets/fx-05-server-name.png" alt="" width="492"><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Alege un șablon

Alege șablonul **CFX Default** pentru moment. Mai există și alte șabloane, dar unele necesită un server de baze de date (XAMPP sau [MariaDB](../vps-dedicated/windows/mariadb-heidisql.md)).

<div align="left"><figure><img src="../.gitbook/assets/fx-06-template.png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Salvează și deschide Recipe Deployer

Apasă **Save** (sau alege altă locație pentru date), apoi mergi la **Recipe Deployer**.

<div align="left"><figure><img src="../.gitbook/assets/fx-07-save.png" alt=""><figcaption><p>Textul scris cu albastru poate diferi, în funcție de locația aleasă de tine.</p></figcaption></figure></div>
{% endstep %}

{% step %}
### Rulează rețeta

Apasă **Next** după ce te asiguri că rețeta arată bine. Ar trebui să fie bine așa cum vine.

<figure><img src="../.gitbook/assets/fx-08-recipe.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

{% hint style="info" %}
Nu uita să deschizi portul `30120` (TCP și UDP). Vezi [Deschiderea porturilor pe Windows](../vps-dedicated/windows/windows-ports.md).
{% endhint %}
