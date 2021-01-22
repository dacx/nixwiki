---
description: How to re-sync your wallet with the NIX network
---

# Syncing Issues

{% hint style="warning" %}
If for whatever reason the following doesn't fix your issue, join the [Discord server](https://discordapp.com/invite/HGuvDTW) and ask in the **public channels only** for help. **Do not respond to any DMs** as scammers might try to trick you into giving them your funds!
{% endhint %}

## QT and GUI Wallets

If you happen to be on the wrong chain \(typically due to not updating your wallet in time before a mandatory update\), your wallet may show an incorrect balance and transactions may fail to send properly.

### How to Resync

First, verify that you are indeed on the wrong chain by comparing your block height to the [explorer](https://blockchain.nixplatform.io/). If they do not match, take the following steps:

1. Be sure you have the latest version of the wallet. If not, download it from [https://nixplatform.io/wallet](https://nixplatform.io/wallet) or [GitHub](https://github.com/NixPlatform/NixCore/releases).
2. Make sure your wallet is not running and navigate to the NIX data directory.
3. If you don't have a backup of your wallet.dat file, now would be a good time to make a copy just in case you accidentally delete it while doing the next step. Check the [Wallet Backup](../../wallet-functionality/qt/backup-and-security/wallet-backup.md) page for more details.
4. Delete the following from the data directory: - blocks \(entire directory\) - chainstate \(entire directory\) - banlist.dat - peers.dat
5. Start the wallet and let it sync. Using a broadband internet connection, it should take about 15 mins to complete.

{% hint style="info" %}
**Default data directory locations:**  
Windows: C:\Users\\(your username\)\AppData\roaming\nix  
Linux: ~/.nix  
MacOS:  ~/Library/Application Support/nix
{% endhint %}

### Optional Steps

{% page-ref page="bootstrap-installation.md" %}

{% page-ref page="manually-adding-peers.md" %}

## CLI Wallets

If your CLI Wallet happens to be on a fork due to not applying mandatory updates in time \(or for any other reason\), the easiest way to correct the issue is to simply delete the blockchain files and let the wallet sync from the beginning.

### Manual Installs

After logging into your VPS:

```text
nix-cli stop
rm -r ~/.nix/{blocks,chainstate}
nixd &
```

### CryptoShark's Scripted Installs

After logging into your VPS:

```text
systemctl stop NIX
rm -r ~/.nix/{blocks,chainstate}
systemctl start NIX
```

### Optional Steps

{% page-ref page="bootstrap-installation.md" %}

{% page-ref page="manually-adding-peers.md" %}

