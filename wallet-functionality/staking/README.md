---
description: NIX Platform Staking Overview
---

# Staking

The NIX network originally began as a lyra2rev2 Proof of Work blockchain. At block 53,000 the consensus method changed to Proof of Stake. To enable this consensus change, a hard fork was necessary. This change to the protocol does not create a new coin, but upgrades the network. As the network matures, staking rewards will increase according to the [Inflation Schedule](../../getting-started/network-and-coin-specs.md#inflation-schedule).

Staking allows users to earn passive income based on their holdings by adding new blocks to the chain without the need of expensive, specialized hardware such as ASIC miners or GPUs which themselves often require access to low electricity costs in order to be profitable. Instead, the chances of creating a new block are correlated to the amount of coins they own and are actively staking.

Staking can be done by the owner directly or they may lease their coins to a [merchant](https://nixplatform.io/marketplace) to stake on their behalf using what is called a ["Leased Proof of Stake" or LPoS contract](lpos-client.md). Users may also utilize LPoS contracts to cold stake their own coins in a much safer environment. It is important to note that when utilizing an LPoS contract, the owner of the coins remains in full control of their holdings and can cancel the contract at any time. The merchant has no ability to move, spend, or otherwise do anything with contracted coins other than actions that are directly related to staking such as creating new blocks and [setting split/combine thresholds](../../advanced-wallet-functions/command-line-options.md#wallet-staking-options).

In order to stake, the coins must be in an address beginning with either "N" or "nix1". Also, the wallet must be encrypted and unlocked for staking, synced with the network, and remain open and running. As of block \#115,921, all unspent transaction outputs \(UTXOs\) require 200 confirmations to becomes available for staking. This also applies to coins which have earned a reward for successfully staking and creating a new block on the chain.

Currently only publicly held NIX can be staked, however, staking [ghosted NIX](../ghost-vault/) is planned.



