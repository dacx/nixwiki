---
description: Earn NIX by helping to secure the network
---

# PoS/LPoS Consensus

The NIX network originally began as a lyra2rev2 Proof of Work blockchain. At block 53,000 the consensus method changed to Proof of Stake. To enable this consensus change, a hard fork was necessary. This change to the protocol does not create a new coin, but upgrades the network. As the network matures, staking rewards will increase according to the [Inflation Schedule](network-and-coin-specs.md#inflation-schedule).

Staking allows users to earn passive income based on their holdings by adding new blocks to the chain without the need of expensive, specialized hardware such as ASIC miners or GPUs which themselves often require access to low electricity costs in order to be profitable. Instead, the chances of creating a new block are correlated to the amount of coins they own and are actively staking.

Staking can be done by the owner directly or they may lease their coins to a [merchant](../support/leased-proof-of-stake-lpos/lpos-merchants.md) to stake on their behalf using what is called a "Leased Proof of Stake" or LPoS contract. Users may also utilize LPoS contracts to cold stake their own coins in a much safer environment. It is important to note that when utilizing an LPoS contract, the owner of the coins remains in full control of their holdings and can cancel the contract at any time. The merchant/cold staking wallet has no ability to move, spend, or otherwise do anything with contracted coins other than actions that are directly related to staking such as creating new blocks and [setting split/combine thresholds](../wallet-functionality/cli/command-line-options.md#wallet-staking-options).

In order to stake, the coins must be in an address beginning with either "N" or "nix1". Also, the wallet must be encrypted and unlocked for staking, synced with the network, and remain open and running. As of block \#115,921, all unspent transaction outputs \(UTXOs\) require 200 confirmations to becomes available for staking. This also applies to coins which have earned a reward for successfully staking and creating a new block on the chain.

Currently only publicly held NIX can be staked, however, staking ghosted NIX is planned.

## In-Wallet Staking

Learn how to stake directly from your QT or GUI wallet.  
[QT Wallet Staking](../wallet-functionality/qt/staking/in-wallet-staking.md)  
[GUI Wallet Staking](../wallet-functionality/gui/staking/in-wallet-staking.md)

## LPoS

Leased Proof of Stake requires a client and server side.

### Server Side

The server side of LPoS does the actual staking by means of a smart contract, allowing you to maintain complete control over your funds while never exposing them to a hot \(online and running\) wallet while they stake. Instructions on how to set one up can be found at:

{% page-ref page="../support/leased-proof-of-stake-lpos/lpos-server-installation.md" %}

### Client Side

Once you have an LPoS server set up, you can then use your qt, gui, or flare wallet containing the funds you wish to stake to create the contract. 

You can find specific instructions for creating an LPoS contract on the following pages..

[QT Wallet](https://wiki.nixplatform.io/home/wallet-functionality/qt/staking/lpos-contracts)  
[GUI Wallet](https://wiki.nixplatform.io/home/wallet-functionality/gui/staking/lpos-contracts)  
[Flare Mobile Wallet](https://wiki.nixplatform.io/home/wallet-functionality/flare-mobile/staking)

Alternatively, you can create a contract with an LPoS merchant for a fee, and they will maintain the server side aspect for you, managing uptime and all required updates to ensure your contracts continue to stake. Be sure you follow their specific instructions, or your contract may not properly stake.

A list of merchants can be found here:

{% page-ref page="../support/leased-proof-of-stake-lpos/lpos-merchants.md" %}

