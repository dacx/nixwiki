# Installation and Updating

It's important to keep on top of wallet updates when operating nixd on a VPS. Wallet updates are often mandatory, but are usually released with a grace period of several days before the operator is required to update.

{% hint style="info" %}
**Important -** if a wallet is not updated by the specified block, the node can become detached from the longest chain and a re-sync will be required. In this scenario, any resulting rewards/fees received on the forked chain are worthless. 
{% endhint %}

### Manual updating

Log into your VPS and use wget to download the latest version:

```bash
wget https://github.com/NixPlatform/NixCore/releases/download/v3.0.8/nix-3.0.8-x86_64-linux-gnu.tar.gz
```

Unpack the file with:

```bash
tar -zxvf nix-3.0.8-x86_64-linux-gnu.tar.gz
```

As the root user, install the binaries with:

```bash
cp nix-3.0.8/bin/* /usr/bin/
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

