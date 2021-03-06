---
description: 2-Way Ghosting allows for both send and receive addresses to be privatized.
---

# 2-Way Ghosting

This never-done-before technology enables the ability to launch powerful private smart contracts on chain while allowing zero knowledge proof transaction edged privacy.

Although the technical procedure for achieving sender and receiver privacy in one transaction is complex in the backstage, it can be summarized as sending coins from one Ghost Vault to another. A brief technical overview can be seen in the [Commitment Key Pack Technical Paper](https://nixplatform.io/wp-content/uploads/2018/10/Commitment_Key_Packs_v1-0-1.pdf). There is a flat rate fee of .1 for these vault to vault transactions, paid from the senders Ghost Vault \(not subtracted from the transaction amount\).

2-Way Ghosting is currently only available in the QT Wallet. Support in other wallets will be available.

## QT Wallet

You must first have [ghosted NIX in your Ghost Vault](1-way-ghosting.md). You can begin your 2-Way Ghost transaction by clicking the "Ghost Vault" button followed by the "Un-Ghost NIX from Vault" tab.

Deselect the "Un-Ghost to Myself" checkbox, enter the recipients Ghost Key in the "Un-Ghost To: " input field and enter an amount of ghosted NIX to send.

![Creating a 2-Way Ghost Transaction](../../.gitbook/assets/qt-2-way-ghosting.png)

{% hint style="info" %}
**NOTE:** Fractional amounts are currently only available in .1 increments.
{% endhint %}

Your 2-Way Ghost transaction will then be added to the blockchain with both send and receive addresses privatized.

![Both send and receive addresses are privatized on the blockchain](../../.gitbook/assets/explorer-2-way-ghosting.png)

