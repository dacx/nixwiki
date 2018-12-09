# Updating Wallet

## **Contents**

1. How to update UI Wallet
2. How to update QT Wallet
3. Updating VPS \(Staking & Ghostnodes\)

## **UI Wallet**

When NIX Core has an available update the UI wallet will automatically download and install the cli on the next instance of the wallet being opened. 

It will also display a notification in the 'Updates' screen if the UI application itself has an available update - download from the [official source](https://nixplatform.io/wallet#download) or direct from GitHub here by choosing your operating system:

{% embed url="https://github.com/NixPlatform/Nix-GUI/releases" %}

{% hint style="success" %}
**Tip -** the UI wallet uses the NIX Core daemon so is affected by NIX Core updates - the wallet auto-updates this side. Manual action is required to install new versions of the UI Wallet itself.
{% endhint %}

## QT Wallet - Manual Update

Download the latest update via the [official source](https://nixplatform.io/wallet#download) or download direct from GitHub below. Check for the release date and version number is as expected and ensure you backup your wallet.dat before proceeding with the install.

{% embed url="https://github.com/NixPlatform/NixCore/releases" %}

## VPS Stakers and Ghostnodes

It's important to keep on top of wallet updates when operating NIX-CLI on a VPS. Wallet updates are often mandatory, but usually with a grace period of several days before the operator is required to update. 

{% hint style="info" %}
**Important -** if a wallet is not updated by the specified block the node can become detached from the longest chain. In this scenario any resulting rewards/fees received on the forked chain are worthless. 
{% endhint %}

### Cryptosharks Easy-Updater

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

### UI Wallet One-Click Updater 

There will soon be a mechanism to automatically update Ghostnodes directly from the UI wallet by inputting only your VPS password. Instructions will be provided in due course.



