---
description: How to set up your own LPoS server.
---

# LPoS Server

## Manual Installation

#### This article will assume you are using a 64 bit Linux Virtual Private Server.

Log into your VPS using a Secure Shell \(ssh\) client according to your providers instructions. [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/) is a popular ssh client that is open source and available for Windows and Unix/Linux for free.

If you are logging in as root, the first thing you will want to do is create a normal user. Running services as the root user is generally considered a bad practice. You can create a new user with:

```bash
useradd -m <username>
```

Next, set a password for your new user.

```bash
passwd <username>
```

Now substitute user into your new user and its home directory using:

```bash
su - <username>
```

{% hint style="success" %}
For future ssh connections, login as your normal user.
{% endhint %}

Download the latest NIX Platform Core software release. At the time of this writing, that would be:

```bash
wget https://github.com/NixPlatform/NixCore/releases/download/v2.3.0/nix-2.3.0-x86_64-linux-gnu.tar.gz
```

Unpack the file.

```bash
tar -zxvf nix-2.3.0-x86_64-linux-gnu.tar.gz
```

Next, make the binary files executable.

```bash
chmod +x nix-2.3.0/bin/*
```

You will now need to be the root user to install the binary files. Use the substitute user command:

```bash
su
```

After entering in your root password, install the NIX binary files.

```bash
cp nix-2.3.0/bin/* /usr/bin/
```

You no longer need root permissions, so drop back down to your normal user with:

```bash
exit
```

Now that you are back into your normal user, start the NIX daemon and put it into the background.

```bash
nixd&
```

Now create your nix.conf file. This needs to be in the data directory, which by default is created as a hidden directory named .nix in the users home. Use the command:

```bash
nano .nix/nix.conf
```

For a minimal configuration, add the following lines to nix.conf:

{% code-tabs %}
{% code-tabs-item title="nix.conf" %}
```text
daemon=1
minimumleasepercentage=1191
leaserewardaddresses=RewardAddress1,RewardAddress2,etc
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Using the above configuration, this wallet will only stake contracts with a fee no less than 11.91% and a reward address of &lt;your\_address\_for\_collecting\_reward\_fees&gt;. For more advanced configurations, see [Command-line options](../../support/command-line-options.md).

Exit and save the file by using 'Ctrl + x', pressing 'y' and hitting &lt;Enter&gt;

{% hint style="success" %}
**TIP:** If you'd like to use this to privately cold stake your own coins, simply omit the 'minimumleasepercentage=' and 'leaserewardaddresses=' lines and create your [LPoS client](lpos-client.md) contract with no fee.
{% endhint %}

Next, encrypt your wallet.

```bash
nix-cli encryptwallet <passphrase>
```

After encryption nixd will automatically shut itself down. Restart the daemon.

```bash
nixd
```

{% hint style="info" %}
**NOTE:** Now that you have 'daemon=1' in your nix.conf file, you will no longer need to append & to nixd in order to put the process into the background.
{% endhint %}

Now you can generate a new address. This will be used for the "Lease To: " address field when creating a [LPoS client](lpos-client.md) contract. The following command will generate and store a new address to a text file named LeaseToAddress.txt:

```text
nix-cli getnewaddress > LeaseToAddress.txt
```

If you want to quickly view the contents of LeaseToAddress.txt, use:

```bash
cat LeaseToAddress.txt
```

{% hint style="success" %}
**TIP:** Now would be a good time to download your wallet.dat, nix.conf and LeaseToAddress.txt files using PuTTY's pscp \(putty secure copy\) program to have a backup.
{% endhint %}

Check to see that your wallet is syncd with:

```bash
nix-cli getblockcount
```

.. and compare the output with the networks current block number. If it continues to read zero, chances are it needs a little help finding a peer. To manually add a node, use:

```bash
nix-cli addnode sf.nixplatform.io add
```

Once you've confirmed your wallet is syncd, unlock it for staking with:

```text
nix-cli walletpassphrase <your_passphrase> 0 true
```

Your VPS wallet is now ready to accept contracts and begin staking.

Finally, delete your bash history to remove your passphrase from both the history file and system memory. 

```bash
history -c;history -w
```

{% hint style="danger" %}
**You should execute this command before logging out any time you enter your password through the bash prompt in plain text.**
{% endhint %}

You can now close your ssh connection.

#### A couple of other useful commands..

To watch your debug file in real time, use:

```bash
tail -f .nix/debug.log
```

To stop nixd, use:

```bash
nix-cli stop
```

## Automatic/Scripted Installation

Alternatively, you can also use the following method and utilize CryptoSharks' script:

These instructions will help guide you to setting up your own cold stake on a VPS. Log into the server using ssh \(Putty for windows or terminal for Mac users\) and run the following commands:

```text
wget -q https://raw.githubusercontent.com/cryptosharks131/Ghostnode/master/nix_cold_stake.sh
bash nix_cold_stake.sh
nix-cli encryptwallet "create_password_here"
nix-cli getnewaddress
nix-cli walletpassphrase "put_your_password_here" 0 true
```

Now you may go to your local wallet and create a LPoS contract with the following details.  
Lease To: This is the address you got from the VPS after running 'nix-cli getnewaddress'  
Amount: The amount to place in the contract \(subtract fee button can be used to take the contract writing fee from this amount\)

You can now hit 'send nix' to confirm the contract and you are all set! Once the contract gets 200 confirms, your VPS will start staking!

Video: [https://youtu.be/GwH5ysdfTrY](https://youtu.be/GwH5ysdfTrY)



