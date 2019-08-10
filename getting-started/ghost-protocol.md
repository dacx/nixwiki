---
description: The most powerful combination of privacy tools ever assembled
---

# Ghost Protocol

The NIX Ghost Protocol consists of a carefully selected and harmonized implementation of privacy elements, providing the user or developer a Swiss Army Knife of privacy options to suit any environment.

Sigma helps anonymize user data by utilizing a cryptographic system that makes it impossible to guess the correct original location of assets. The addition of Commitment Key Packs create a blockchain element that conceals the destination resulting in a non-traceable address location. When used together, these two mechanisms provide full sender and receiver privacy. Integrated with Dandelion++ and a layering of Tor networking, users will have both blockchain privacy as well as networking and transaction broadcast privacy.

## Sigma Protocol

To solve the dilemma of anonymous transactions, Bitcoin and preceding alternative cryptocurrencies have attempted to use transaction mixers or ring signatures. However, there are a number of drawbacks to these proposed solutions. For one, a malicious or compromised member of a mixer or ring signature can break privacy. Furthermore, the anonymity set is a key metric to understanding how private a currency is. Privacy in formerly proposed solutions is limited by the size of the mixing cycle or ring signature. Each mixing cycle or ring signature is controlled by the number of transactions per cycle, which is transitively limited by the block size of the currency. Thus, the anonymity set in previous attempts at privacy tends to only be a few hundred transactions.

The Sigma Protocol uses a 3-move structure \(commitment, challenge and response\) that allows a prover to convince a verifier that a statement is true. Sigma improves over the previously used Zerocoin Protocol to solve 2 major drawbacks. First, it does not rely on a trusted setup of initial parameters in any way, where a “setup ceremony” is required to get things started. Secondly, it greatly reduces the on-chain proof size which enables greater scalability. In addition to these 2 improvements, the cryptographic assumptions are much easier to audit.

## Commitment Key Packs

While the Sigma Protocol provides privacy for the sender, the NIX fully custom Commitment Key Pack scheme for Pedersen Anonymous Deposits provides complete sender and receiver privacy in one transaction. This scheme enables full Zero-Knowledge proof transaction privacy between both sender and receiver, known as the 2-Way Ghosting mechanism via Ghost Keys and Ghost Key QR codes.

Read the technical paper for Commitment Key Packs [here](https://nixplatform.io/wp-content/uploads/2018/10/Commitment_Key_Packs_v1-0-1.pdf).

## Tor Anonymity Network

Tor is a software that enables the ability to conceal user location and usage from outside monitoring entities. When using Tor, a user’s networking is routed through thousands of different network relays to scramble initial internet traffic resulting in a secure system for networking. Tor will be a default networking tool enabled in the NIX Platform.

## Dandelion ++ Broadcast Anonymity

The Dandelion++ Protocol obscures the network origin of a transaction by initially broadcasting to only 1 random peer using a privacy graph, who then does the same. As this continues it forms a length of single hops known as a “stem” until eventually, and randomly, the transaction is ready to be diffused. At this point, a “fluff” phase begins where the transaction is broadcast to all connected peers, on and on to quickly propagate across the entire network as normal. To the observer wishing to reveal the original sending node, the closest they can get with any certainty is the last hop in the “stem”.

