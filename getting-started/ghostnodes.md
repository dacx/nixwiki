---
description: The NIX utility-driven masternode
---

# Ghostnodes

NIX Ghostnodes are a fundamental part of the NIX protocol layer and are responsible for processing and validating privacy transactions as well as approving and fulfilling cross-chain protocols. All smart contract elements requiring autonomous privacy processing rely on NIX Ghostnodes to fulfill those requests.

Running a Ghostnode requires a collateral of 40,000 NIX and are rewarded in the following ways:

1. Block rewards -- A percentage of new block rewards are paid to Ghostnodes by a serialized method which cycles through the list of active nodes.
2. Ghosting NIX -- When a user ghosts their coins either to their own or to another user's Ghost Vault, a 0.25% fee is collected.
3. Vault to vault private transactions -- Users moving ghosted NIX from vault to vault \(full sender and receiver privacy transactions\) incur a .1 flat rate fee.

Privacy transaction fees are pooled and then split every 720 blocks \(~24 hours\) among all active Ghostnodes.

## How to Setup Your Ghostnode

There are 2 sides involved to successfully operate Ghostnodes:

### **Server Side**

This is where all of the work is done. You can either setup and maintain your own server using a VPS, or you can pay a hosting provider to keep your node updated and running smoothly for you. Coins are **not stored** on the server side.

You can find instructions setting up the server side here:

{% page-ref page="../support/ghostnodes/" %}



### **Client Side**

This is your supported NIX wallet where your collateral is stored and remains under your full and complete control.

Instructions for each individual wallet can be found on the following page:

{% page-ref page="../support/ghostnodes/client-side/" %}

