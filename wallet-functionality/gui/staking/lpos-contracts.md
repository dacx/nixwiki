---
description: How to use LPoS contracts in your UI wallet
---

# LPoS Contracts

## Creating a Contract

First, click on "Staking" in the left-hand menu, then "Leased staking" followed by "NEW LEASING CONTRACT"

![](../../../.gitbook/assets/ui-lpos-composite.png)

![New leasing contract screen](../../../.gitbook/assets/ui-lpos-setup.png)

**`LPoS provider details:`** Can be set to anything you like.

**`Address that coins will be leased to for staking:`** Defines the external address allowed to stake the coins. This address is supplied by the merchant.

**`Contract description:`** Can be set to anything you like.

**`LPoS provider's fee:`** Amount of reward share allocated to the leasing merchant. This info is provided by the merchant.

**`Address for LPoS provider's fee:`** The merchant's address for their share of the stake reward when your contract successfully stakes. This address is supplied by the merchant.

## Cancelling a Contract

At the bottom of the Leased Staking window, you'll find the active contracts list. Here, you can view details and cancel any of your LPoS contracts.

![](../../../.gitbook/assets/ui-lpos-contracts.png)

{% hint style="info" %}
**NOTE:** Active contracts that have recently hit a stake will not show until those coins have matured \(201 confirmations\).
{% endhint %}

## More Information

You can find a list of LPoS merchants or learn how to install your own cold staking server here:

{% page-ref page="../../../support/leased-proof-of-stake-lpos/" %}

