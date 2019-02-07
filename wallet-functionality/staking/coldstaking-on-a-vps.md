---
description: How to set up your own LPoS server.
---

# Coldstaking on a VPS

Log into your VPS using a Secure Shell \(ssh\) client according to your providers instructions. [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/) is a popular ssh client that is open source and available for Windows and Unix/Linux for free.

From here it will be assumed that you are running commands as root. You can of course also use a regular user with elevated permissions.

Download the latest NIX Platform Core software release. At the time of this writing, that would be:

```bash
wget https://github.com/NixPlatform/NixCore/releases/download/v2.2.0.1/nix-2.2.0-x86_64-linux-gnu.tar.gz
```

Unpack the file.

```bash
tar -zxvf nix-2.2.0-x86_64-linux-gnu.tar.gz
```

Install the NIX binary files.

```bash
cp nix-2.2.0/bin/* /usr/bin/
```

Start the NIX daemon and put it into the background.

```bash
nixd&
```

Now create your nix.conf file.

```bash
nano .nix/nix.conf
```

For a minimal configuration, add the following lines to nix.conf:

```text
daemon=1
minimumleasepercentage=1191
leaserewardaddresses=<your_address_for_collecting_reward_fees>
```

Using the above configuration, this wallet will only stake contracts with a fee no less than 11.91% and a reward address of &lt;your\_address\_for\_collecting\_reward\_fees&gt;.

Exit and save the file by using 'Ctrl + x', pressing 'y' and hitting &lt;Enter&gt;

{% hint style="success" %}
**TIP:** If you'd like to use this to privately cold stake your own coins, simply omit the 'minimumleasepercentage=' and 'leaserewardaddresses=' lines and create your LPoS contract with no fee.
{% endhint %}

Next, stop the daemon and encrypt your wallet.

```bash
nix-cli stop
nix-cli encryptwallet <passphrase>
```

Restart the daemon.

```bash
nixd
```

{% hint style="info" %}
**NOTE:** Now that you have 'daemon=1' in your nix.conf file, you will no longer need to append & to nixd in order to put the process into the background.
{% endhint %}

Now you can generate a new address. This will be used for the "Lease To: " address field when creating a LPoS contract. The following command will generate and store a new address to a text file named LeaseToAddress.txt:

```text
nix-cli getnewaddress > LeaseToAddress.txt
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



Alternatively, you can also use the following method and utulize CryptoSharks' script:

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



