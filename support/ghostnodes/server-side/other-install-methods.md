---
description: VPS Ghostnode installation instructions
---

# VPS Install

## Manual Installation

This guide will assume you are using Ubuntu 18.04 LTS as your VPS Operating System.

Connect to your VPS using an SSH connection. [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) is a popular choice for Windows users to do this with. Your VPS host will provide you with a username and ip address to make this connection.

Once you have logged in, you'll need to download NIX wallet.

```bash
wget https://github.com/NixPlatform/NixCore/releases/download/v3.0.8/nix-3.0.8-x86_64-linux-gnu.tar.gz 
```

Next, unpack the download.

```bash
tar zxvf nix-3.0.8-x86_64-linux-gnu.tar.gz 
```

Copy the binary files to /usr/bin/

```bash
sudo cp nix-3.0.8/bin/* /usr/bin/
```

Before we start the wallet, lets go ahead and create the configuration file.

```bash
mkdir .nix
nano .nix/nix.conf
```

Add the following lines to the nix.conf:

{% code title="~/.nix/nix.conf" %}
```bash
rpcallowip=127.0.0.1
daemon=1
maxconnections=64
ghostnode=1
externalip=your_ghostnode_ip_address_here(same IP you used to ssh to)
ghostnodeprivkey=your_ghostnode_key_here
```
{% endcode %}

{% hint style="success" %}
Don't forget to add the connection port \(6217\) to your IP address.  
Example: 192.168.0.1:6214
{% endhint %}

{% hint style="info" %}
You can get a ghostnodeprivkey from either the client or server side by running:  
ghostnode genkey  
in a QT/GUI debug console, nix-cli, or provided by Flare Mobile.
{% endhint %}

Use Ctrl+X to exit nano, and Y followed by &lt;Enter&gt; to save changes.

You can now start the nix wallet with:

```bash
nixd
```

The wallet will now sync with the blockchain. If for some reason it's having trouble, you can manually add some official peers and/or install a bootstrap by following the instructions for the CLI wallet in the following guides:

{% page-ref page="../../syncing-issues/manually-adding-peers.md" %}

{% page-ref page="../../syncing-issues/bootstrap-installation.md" %}

To check the status of the sync:

```bash
nix-cli getblockchaininfo | grep blocks
```

Compare the result with a block explorer to verify your wallet is fully sync'd. Once finished, your Ghostnode VPS is ready to use.

### Security

It is recommended that you install some basic firewall security. While the options are plentiful and configurations endless, this is by no means the only way to do it.

You can run the following commands to setup a basic firewall:

```bash
sudo apt-get install ufw
sudo ufw allow ssh/tcp
sudo ufw limit ssh/tcp
sudo ufw allow 6214/tcp
sudo ufw logging on
sudo ufw enable
```

## Bash Script from CryptoSharks

This installation is also automated but needs a bit more technical understanding of ssh connections. You can find all required information on his [GitHub Repository](https://github.com/cryptosharks131/Ghostnode).

