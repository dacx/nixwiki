---
description: How to restore your QT wallet.dat file
---

# Wallet Restoration

The method of restoring a Core wallet.dat file is essentially the reverse of [manually backing it up](wallet-backup.md#manual-backup). Default locations for each Operating System can be found below.

## Windows

By default, the NIX data directory will be created as C:\Users\\(your username\)\AppData\roaming\nix\

{% hint style="success" %}
**TIP:** Windows hides the AppData folder by default when using the graphical file explorer. In order to get inside the AppData folder, you can either type "%AppData%" into the search bar or check the box for "Hidden items" under the View menu to show hidden files in the file explorer window and navigate your way there.
{% endhint %}

To restore a backed up wallet.dat file, simply copy it into the following location:

{% hint style="info" %}
**NOTE:** If a "wallets" directory exists, the software will use it as the default wallet directory. If it does not exist, then the root directory will be used.
{% endhint %}

C:\Users\\(your username\)\AppData\roaming\nix\wallets\wallet.dat

or

C:\Users\\(your username\)\AppData\roaming\nix\wallet.dat

## MacOS

Be default, the NIX data directory will be created as ~/Library/Application Support/nix/

{% hint style="success" %}
**TIP:** MacOS hides the Application Support folder by default.  
1. On the top bar, left side of your screen click on "Go", then click on "Go to Folder".  
2. Type or copy-paste: ~/Library/Application Support/nix/
{% endhint %}

To restore a backed up wallet.dat file, simply copy it into the following location:

{% hint style="info" %}
**NOTE:** If a "wallets" directory exists, the software will use it as the default wallet directory. If it does not exist, then the root directory will be used.
{% endhint %}

~/Library/Application Support/nix/wallets/wallet.dat

or

~/Library/Application Support/nix/wallet.dat

## Linux

By default, the NIX data directory will be created as ~/.nix/

To restore a backed up wallet.dat file, simply copy it into the following location:

{% hint style="info" %}
**NOTE:** If a "wallets" directory exists, the software will use it as the default wallet directory. If it does not exist, then the root directory will be used.
{% endhint %}

~/.nix/wallets/wallet.dat

or

~/.nix/wallet.dat

