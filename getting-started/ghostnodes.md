---
description: The NIX utility-driven masternode
---

# Ghostnodes

NIX Ghostnodes are a fundamental part of the NIX protocol layer and are responsible for processing and validating privacy transactions as well as approving and fulfilling cross-chain protocols. All smart contract elements requiring autonomous privacy processing rely on NIX Ghostnodes to fulfill those requests.

Running a Ghostnode requires a collateral of 40,000 NIX and are rewarded in the following ways:

1. Block rewards -- A percentage of new block rewards are paid to Ghostnodes by a serialized method which cycles through the list of active nodes. The current block reward for a Ghostnode is 8.448 NIX.
2. Ghosting NIX -- When a user ghosts their coins either to their own or to another user's Ghost Vault, a 0.25% fee is collected.
3. Vault to vault private transactions -- Users moving ghosted NIX from vault to vault \(full sender and receiver privacy transactions\) incur a .1 flat rate fee.

Privacy transaction fees are pooled and then split every 720 blocks \(~24 hours\) among all active Ghostnodes.

### Looking for detailed instructions on how to run a Ghostnode?

{% page-ref page="../support/ghostnodes/" %}

