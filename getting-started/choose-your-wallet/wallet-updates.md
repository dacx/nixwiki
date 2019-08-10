# Wallet Updates

## **GUI Wallet**

When NIX Core has an available update the GUI wallet will automatically download and install the daemon, making the latest version available for use the next time you run your wallet. 

When the GUI itself has an available update, a notification will appear in the "Updates" screen. These updates require the user to download and install the latest version from the [NIX website](https://nixplatform.io/wallet#download) or direct from [GitHub](https://github.com/NixPlatform/Nix-GUI/releases).

## QT Wallet

Download the latest update for your specific Operating System via the [NIX website](https://nixplatform.io/wallet#download) or direct from [GitHub](https://github.com/NixPlatform/NixCore/releases). For MacOS and Windows, simply click on the file to begin installation. For all others, unpack the .tar.gz file and copy the binaries from the bin/ directory to the appropriate location to install for all users, or simply execute them from where ever you unpacked them if no other users need access.

## VPS Staking and Ghostnodes

It's important to keep on top of wallet updates when operating nixd on a VPS. Wallet updates are often mandatory, but are usually released with a grace period of several days before the operator is required to update.

{% hint style="info" %}
**Important -** if a wallet is not updated by the specified block the node can become detached from the longest chain. In this scenario any resulting rewards/fees received on the forked chain are worthless. 
{% endhint %}

### Manual updating

Log into your VPS and use wget to download the latest version:

```bash
wget https://github.com/NixPlatform/NixCore/releases/download/v3.0.4/nix-3.0.4-x86_64-linux-gnu.tar.gz
```

Unpack the file with:

```bash
tar -zxvf nix-3.0.4-x86_64-linux-gnu.tar.gz
```

As the root user, install the binaries with:

```bash
cp nix-3.0.4/bin/* /usr/bin/
```

### Cryptosharks Easy-Updater

If you used the auto-installer script from CryptoSharks, you'll need to use his auto-updater to bring your VPS up to date with the latest version. The update script itself needs to get updated so wait until it's ready. 

Update the script with: 

```bash
rm nix_update.sh* wget -q https://raw.githubusercontent.com/cryptosharks131/Ghostnode/master/nix_update.sh 
./nix_update.sh
```

If used for staking, unlock with:

```text
nix-cli walletpassphrase YOURWALLETPASSPHRASE 0 true
```

Finally, delete your bash history to remove your passphrase from both the history file and system memory.

```bash
history -c;history -w
```

