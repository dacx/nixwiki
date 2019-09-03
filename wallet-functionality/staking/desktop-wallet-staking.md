# Wallet Staking

## QT Wallet

In order to stake your coins from the QT Wallet you must first [encrypt your wallet](../backup-and-security-1/qt-wallet-encryption.md). You cannot stake from a wallet that is not encrypted. Further, you can only stake coins from an address that beings with either "N" or "nix1". Choosing which type of address to stake from depends on whether or not you wish to participate in [Governance Voting](../governance-voting.md). Addresses beginning with "nix1" are eligible to vote, while "N" addresses are not.

To get started, first make sure your coins are in an "N" or "nix1" address and simply select "Unlock For Staking..." from the Settings menu. You will then be prompted to enter your wallet passphrase.

![Select &quot;Unlock For Staking...&quot; from the Settings Menu](../../.gitbook/assets/qt-unlockforstakingmenu.png)

![Enter in your passphrase](../../.gitbook/assets/qt-stakepass.png)

![Staking is Enabled](../../.gitbook/assets/qt-stakingenabled.png)

{% hint style="warning" %}
**IMPORTANT:** You must leave your wallet open and "unlocked for staking" in order to actively stake your coins! If you'd rather not leave your wallet open 24/7, consider using an [LPoS Merchant](https://nixplatform.io/marketplace).
{% endhint %}

## GUI Wallet

Staking with the GUI Wallet is quite easy as well. Simply select "Staking" from the left-hand menu of the wallet and toggle the staking slider. You will then be prompted to enter in your wallet passphrase. 

![Select &quot;Staking&quot; from the left-hand menu](../../.gitbook/assets/ui-stakingmenu.png)

![Toggle the &quot;Staking&quot; slider](../../.gitbook/assets/ui-staking.png)

![Enter in your passphrase](../../.gitbook/assets/ui-stakepass.png)

![Staking is enabled](../../.gitbook/assets/ui-stakingon.png)

{% hint style="warning" %}
**IMPORTANT:** You must leave your wallet open and "unlocked for staking" in order to actively stake your coins!  If you'd rather not leave your wallet open 24/7, consider using an [LPoS Merchant](https://nixplatform.io/marketplace).
{% endhint %}

## Advanced Configuration

You can enact finer control over staking by using [Wallet staking options](../command-line-options.md#wallet-staking-options) in your nix.conf configuration file.

