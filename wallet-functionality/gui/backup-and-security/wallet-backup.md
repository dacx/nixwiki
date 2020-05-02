---
description: How to backup your UI wallet
---

# Wallet Backup

## Backup Frequency

Because the NIX GUI wallet utilizes HD key generation, you do not need to backup your wallet after generating 100 or 1000 receive addresses. All receive addresses you generate are based off of a single master private key which will grant you access to all future generated addresses.

{% hint style="warning" %}
**NOTICE:** Changing your password will not require a new backup, but any old backups will still use their respective password. Therefore, it is strongly recommended that you replace any previous wallet.dat backups.
{% endhint %}

{% hint style="danger" %}
**WARNING:** Ghost Vault funds are handled differently than public coins and require backups after any use of a ghost vault key \(which includes sending to your own vault\). The wallet automatically creates an updated backup file in the ghostbackups directory any time your ghost vault is used. This backup file is not in addition to your normal wallet.dat file, it is simply a recent backup of it.
{% endhint %}

## Backing up your wallet

You can manually copy your wallet.dat file to a new location by navigating to the NIX data directory and making a copy of the wallet.dat. The default location for this file is inside the wallets directory if it exists, otherwise, the root data directory \(nix\).

### Windows

{% hint style="success" %}
**TIP:** Windows hides the AppData folder by default when using the graphical file explorer. In order to get inside the AppData folder, you can either type "%AppData%" into the search bar or check the box for "Hidden items" under the View menu to show hidden files in the file explorer window and navigate your way there.
{% endhint %}

C:\Users\\(your username\)\AppData\roaming\nix\wallets\wallet.dat

or

C:\Users\\(your username\)\AppData\roaming\nix\wallet.dat

{% hint style="info" %}
**NOTE:** If a "wallets" directory exists, the software will use it as the default wallet directory. If it does not exist, then the root directory will be used.
{% endhint %}

### MacOS

{% hint style="success" %}
**TIP:** MacOS hides the Application Support folder by default.  
1. On the top bar, left side of your screen click on "Go", then click on "Go to Folder".  
2. Type or copy-paste: ~/Library/Application Support/nix/
{% endhint %}

~/Library/Application Support/nix/wallets/wallet.dat

or

~/Library/Application Support/nix/wallet.dat

{% hint style="info" %}
**NOTE:** If a "wallets" directory exists, the software will use it as the default wallet directory. If it does not exist, then the root directory will be used.
{% endhint %}

### Linux

~/.nix/wallets/wallet.dat

or

~/.nix/wallet.dat

{% hint style="info" %}
**NOTE:** If a "wallets" directory exists, the software will use it as the default wallet directory. If it does not exist, then the root directory will be used.
{% endhint %}

