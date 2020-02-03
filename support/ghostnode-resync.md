# Ghostnode Resync

**Script Installs, e.g. CryptoSharks method:**

```text
systemctl stop NIX
rm -r ~/.nix/{blocks,chainstate,peers.dat,banlist.dat}
systemctl start NIX
```

 **Manual Installs:**

```text
nix-cli stop
rm -r ~/.nix/{blocks,chainstate,peers.dat,banlist.dat}
nixd &
```

#### Downloading a bootstrap \(optional\)

The following instructions assume a VPS running Ubuntu 18.04. Perform this action after stopping the wallet and deleting the files \(steps 1 and 2 above\). After unzipping the bootstrap file, continue on to step 3.

First, you'll need to install python-pip, gdown, and unzip if they are not already.

```text
sudo apt update
sudo apt install python-pip
sudo -H pip install gdown
sudo apt install unzip
```

Download and unzip the bootstrap file:

```text
gdown https://drive.google.com/uc?id=1GbLWYGMBe0BIMJDTmN5iOqVTN6ekaXiK
unzip NIXBlockchain-352122.zip -d ~/.nix
```

{% hint style="warning" %}
If for whatever reason these steps don't fix your issue, join the [Discord server](https://discordapp.com/invite/HGuvDTW) and ask in the **public channels only** for help. **Do not respond to any DMs** as scammers might try to trick you into giving them your funds!
{% endhint %}

