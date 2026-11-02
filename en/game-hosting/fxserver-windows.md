---
description: "Install and start a FiveM FXServer on Windows with the Cfx.re recipe deployer."
icon: windows
---

# FXServer on Windows

This guide installs a FiveM server (FXServer) on a Windows VPS or dedicated server.

{% hint style="warning" %}
You need a **Cfx.re account** to link and run the server.
{% endhint %}

{% stepper %}
{% step %}
### Check the files

Make sure all the necessary files are present in the extracted directory to avoid startup errors. When the files are correctly downloaded and in place, continue with starting the server.
{% endstep %}

{% step %}
### Start the server

Double-click `FXServer.exe`, or launch it from CMD/Terminal.

<div align="left"><figure><img src="../.gitbook/assets/fx-01-launch.png" alt="" width="470"><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Link your account with the PIN

A page should open in your browser. Make sure the PIN is filled in and click **Link Account**.

<div align="left"><figure><img src="../.gitbook/assets/fx-02-pin.png" alt="" width="437"><figcaption><p>You can find the code in the console that opened together with the .exe</p></figcaption></figure></div>
{% endstep %}

{% step %}
### Log in to Cfx.re

Log in to your Cfx.re account in this tab, then click **Yes, Allow**.

<div align="left"><figure><img src="../.gitbook/assets/fx-03-login.png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Set a password and accept the terms

1. Set a password to access your server's administration page.
2. Accept the terms and conditions.

<div align="left"><figure><img src="../.gitbook/assets/fx-04-password-terms.png" alt="" width="407"><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Name your server

Enter a name for your server and click **Next**, then select **Popular Recipes**.

<div align="left"><figure><img src="../.gitbook/assets/fx-05-server-name.png" alt="" width="492"><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Choose a template

Choose the **CFX Default** template for now. Other templates exist, but some of them need a database server (XAMPP or [MariaDB](../vps-dedicated/windows/mariadb-heidisql.md)).

<div align="left"><figure><img src="../.gitbook/assets/fx-06-template.png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
### Save and open the Recipe Deployer

Click **Save** (or choose a different path for the data), then go to **Recipe Deployer**.

<div align="left"><figure><img src="../.gitbook/assets/fx-07-save.png" alt=""><figcaption><p>The text in blue may differ, depending on the path you selected.</p></figcaption></figure></div>
{% endstep %}

{% step %}
### Deploy the recipe

Click **Next** after checking that the recipe looks good. It should be fine as it comes.

<figure><img src="../.gitbook/assets/fx-08-recipe.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

{% hint style="info" %}
Remember to open port `30120` (TCP and UDP). See [Open ports on Windows](../vps-dedicated/windows/windows-ports.md).
{% endhint %}
