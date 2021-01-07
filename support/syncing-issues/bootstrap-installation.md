---
description: Bootstrap installation instructions
---

# Bootstrap Installation

{% hint style="warning" %}
If for whatever reason the following doesn't fix your issue, join the [Discord server](https://discordapp.com/invite/HGuvDTW) and ask in the **public channels only** for help. **Do not respond to any DMs** as scammers might try to trick you into giving them your funds!
{% endhint %}

## QT/GUI Wallets

1. Download the [NIX Blockchain Bootstrap](https://drive.google.com/drive/u/1/folders/1NepcvQ-GpgxNmBvcCnD5TltaXqIgECcM) file.
2. Close/shutdown your wallet.
3. Navigate to the NIX data directory.
4. Delete blocks and chainstate directories.
5. Unzip contents of the bootstrap .zip file to the [NIX data directory](../default-data-directory.md).
6. Restart your wallet.

## CLI Wallet

First, stop the wallet and delete the blocks and chainstate directories. Though not necessarily required, you might also want to delete the peers and banlist files.

```text
nix-cli stop
rm -r ~/.nix/{blocks,chainstate,peers.dat,banlist.dat}
```

{% hint style="info" %}
**NOTE:** If you used Crypto Sharks' script to install, use "systemctl stop NIX" instead of "nix-cli stop"
{% endhint %}

You can use wget or gdown to download the file..

### wget

```bash
wget --load-cookies /tmp/cookies.txt "https://docs.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=1s8tb5AOentOsy4A8jMoqfFsPVhiyMyWH' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=1s8tb5AOentOsy4A8jMoqfFsPVhiyMyWH" -O NIXBlockchain-600475.zip && rm -rf /tmp/cookies.txt
unzip NIXBlockchain-600475.zip -d ~/.nix
```

If your system does not have wget and unzip already installed \(commands assume Ubuntu Linux\):

```bash
sudo apt update
sudo apt install wget
sudo apt install unzip
```

### gdown

```text
gdown https://drive.google.com/file/d/1s8tb5AOentOsy4A8jMoqfFsPVhiyMyWH
unzip NIXBlockchain-600475.zip -d ~/.nix
```

If your system does not have python-pip, gdown, and unzip already installed \(commands assume Ubuntu Linux\):

```text
sudo apt update
sudo apt install python-pip
sudo -H pip install gdown
sudo apt install unzip
```



Restart your wallet.

```bash
nixd &
```

{% hint style="info" %}
**NOTE:** If you used Crypto Sharks' script to install, use "systemctl start NIX" instead of "nixd &"
{% endhint %}

