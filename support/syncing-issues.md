# Syncing Issues

{% hint style="warning" %}
If for whatever reason the following doesn't fix your issue, join the [Discord server](https://discordapp.com/invite/HGuvDTW) and ask in the **public channels only** for help. **Do not respond to any DMs** as scammers might try to trick you into giving them your funds!
{% endhint %}

If you happen to be on the wrong chain \(typically due to not updating your wallet in time before a mandatory update\), your wallet may show an incorrect balance and any transactions you try to send will not be properly received.

## How to Resync

First, verify that you are indeed on the wrong chain by comparing your block height to the [explorer](https://blockchain.nixplatform.io/). If they do not match, take the following steps:

1. Be sure you have the latest version of the wallet. If not, download it from [https://nixplatform.io/wallet](https://nixplatform.io/wallet) or [GitHub](https://github.com/NixPlatform/NixCore/releases).
2. Make sure your wallet is not running and navigate to the NIX data directory \(see [Finding the NIX data directory](syncing-issues.md#finding-the-nix-data-directory) below\). 
3. If you don't have a backup of your wallet.dat file, now would be a good time to make a copy just in case you accidentally delete it while doing the next step. Check the [Wallet Backup](../wallet-functionality/backup-and-security-1/wallet-backup.md) page for more details.
4. Delete the following from the data directory: - blocks \(entire directory\) - chainstate \(entire directory\) - banlist.dat - peers.dat
5. Start the wallet and let it sync. Using a broadband internet connection, it should take about 15 mins to complete.

### Optional Steps

#### Download and install a bootstrap after completing step 4

1. Download the latest [NIX Blockchain Bootstrap](https://drive.google.com/open?id=1GbLWYGMBe0BIMJDTmN5iOqVTN6ekaXiK) file \(Block Height: 352122\).
2. Unzip contents to the NIX data directory.

#### Manually adding peers

Once you've restarted your wallet to sync, you can use the debug console to quickly add an official peer that is geographically closest to you by typing:

```text
addnode ny.nixplatform.io add
```

![Successfully adding the ny.nixplatform.io node](../.gitbook/assets/console-addnode.png)

**List of official nodes:**

* ny.nixplatform.io \(United States\)
* sf.nixplatform.io \(United States\)
* ldn.nixplatform.io \(England\)
* fra.nixplatform.io \(Germany\)
* tor.nixplatform.io \(Canada\)
* sgp.nixplatform.io \(Singapore\)
* blr.nixplatform.io \(India\)

## Finding the NIX data directory

#### Windows

1. Hit Windows Key + R.
2. Type `%appdata%` and hit Enter.
3. Click on the `nix` directory.

#### Linux

1. The data directory is located in `~./nix` .

#### Mac OS

1. In the Top Bar locate and click `Go -> Go to Folder` .
2. Paste `~/Library/Application Support/nix/` and hit Enter.

