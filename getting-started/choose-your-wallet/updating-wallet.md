# Updating Wallet

## **UI Wallet -** Automatic Update

Auto-update

## QT Wallet - Manual Update

Manual update

## VPS Stakers and Ghostnodes

It's important to keep on top of wallet updates when operating NIX-CLI on a VPS. Wallet updates are often mandatory, usually with a grace period of several days before the operator is required to update. 

{% hint style="info" %}
**Important -** if a wallet is not updated by the specified block the node can become detached from the longest chain. In this scenario any resulting rewards/fees received on the forked chain are worthless. 
{% endhint %}

### Cryptosharks Auto-Updater

If you used the auto-installer script from @CryptoSharks\#7581 you'll need to use his auto-updater to bring your VPS up to date with the latest version. The update script itself needs to get updated so wait until it's ready. 

Remember to unlock for staking and clear history once it's finished. 

* Update script: 

```text
rm nix_update.sh* wget -q 
https://raw.githubusercontent.com/cryptosharks131/Ghostnode/master/nix_update.sh 
bash nix_update.sh
```

* Unlock for staking: 

`nix-cli walletpassphrase 'YOURWALLETPASSPHRASE' 0 true` 

* Clear history:

`cat /dev/null > ~/.bash_history && history -c`



