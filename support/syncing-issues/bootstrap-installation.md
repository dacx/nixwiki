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

If your system does not have python-pip, gdown, and unzip already installed \(commands assume Ubuntu Linux\):

```text
sudo apt update
sudo apt install python-pip
sudo -H pip install gdown
sudo apt install unzip
```

Download and unzip the bootstrap file:

```text
gdown https://drive.google.com/file/d/1mZ-0n9N2pyJZnjfAT9X7MLob1nWasb-o
unzip NIXBlockchain-576781.zip -d ~/.nix
```

Restart your wallet.

```bash
nixd &
```

{% hint style="info" %}
**NOTE:** If you used Crypto Sharks' script to install, use "systemctl start NIX" instead of "nixd &"
{% endhint %}

