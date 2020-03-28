---
description: Common staking issues
---

# Staking Issues

{% hint style="info" %}
**NOTE:** If the Discord info-bot gave you a time between stakes, please remember that this is only an estimate based on info available at that exact moment and can fluctuate wildly depending on changing network difficulty and a certain degree of luck, both good and bad.
{% endhint %}

## QT, GUI and CLI Wallets

{% hint style="success" %}
Sometimes when using the staking function in the UI Wallet, the switch may indicate that staking is turned off. This is a visual display bug/glitch. You can learn how to verify whether or not staking is enabled below.
{% endhint %}

**Outdated wallet version**  
Check the [NIX website](https://nixplatform.io/wallet) or [github repository](https://github.com/nixplatform/) to make sure you are running the latest version of the wallet.

**Wallet is not properly sync'd**  
Compare your wallets block height with a [blockchain explorer](https://chainz.cryptoid.info/nix/). If your wallet shows something different, [re-sync your wallet](syncing-issues/).

**Wallet is locked**  
You must unlock your wallet and provide your encryption passphrase to enable staking.

**Wallet is not running**  
Your wallet must remain open and running to find new blocks. If you'd rather not keep it open, consider using an [LPoS Merchant](https://nixplatform.io/marketplace).

**Attempting to stake from an address that begins with G**  
Only addresses beginning with N or nix1 are eligible for staking. Further, only nix1 addresses are eligible for Governance Voting.

## Verify Staking is Enabled

You can verify whether or not the wallet is actually staking by navigating to the console and running the command "getstakinginfo" \(or `nix-cli getstakinginfo` for CLI wallets\). If the output shows the following two lines as shown, your wallet is staking.

> "enabled": 1,  
> "staking": 1,

{% hint style="warning" %}
If for whatever reason these don't fix your issue, join the [Discord server](https://discordapp.com/invite/HGuvDTW) and ask in the **public channels only** for help. **Do not respond to any DMs** as scammers might try to trick you into giving them your funds!
{% endhint %}

