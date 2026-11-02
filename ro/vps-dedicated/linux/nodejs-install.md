---
description: "Instalează Node.js pe Linux cu NVM (Node Version Manager)."
icon: node-js
---

# Instalarea Node.js

Ca să instalezi Node.js pe Linux recomandăm NVM (Node Version Manager), care îți permite să instalezi și să schimbi între mai multe versiuni de Node.js.

## Instalează NVM

```bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

După instalare, reconectează-te la SSH sau rulează:

```bash
. ~/.bashrc
```

Acum NVM este disponibil prin comanda `nvm`.

## Comenzi utile

{% tabs %}
{% tab title="Verifică versiuni" %}
Vezi versiunile de Node.js instalate:

```bash
nvm list
```

Verifică ce versiune folosești acum:

```bash
nvm current
```

```bash
nvm version
```
{% endtab %}

{% tab title="Instalează" %}
Instalează versiunea dorită:

```bash
nvm install <versiune_nodejs>
```
{% endtab %}

{% tab title="Schimbă" %}
Schimbă versiunea (are sens doar dacă ai instalate mai multe):

```bash
nvm use <versiune_nodejs>
```

Setează o versiune implicită:

```bash
nvm alias default <versiune_nodejs>
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Comenzile acceptă versiuni majore, de exemplu `16`, `18` sau `20`. Nu e nevoie să scrii formatul complet `xx.xx.xx`.
{% endhint %}
