# Ghost Protocol

The NIX Ghost Protocol is a collection of 4 different privacy elements which allows users and developers both the options they need to ensure not only fungible coin transactions but also network and broadcast privacy.

## Sigma Protocol

Developed by the [ZCoin](https://zcoin.io/) team, Sigma is a zero-knowledge proof protocol which essentially allows users to burn and later re-issue \(or mint\) public coins with no attached history. Sigma improves over the previously used Zerocoin Protocol by not requiring a trusted "setup ceremony" of any kind and significantly decreases transaction size allowing for greater scaling.

The detailed underlying concept for Sigma can be found [here](https://eprint.iacr.org/2014/764.pdf).

## Commitment Key Packs

Used alone, CKPs \(known as "Ghost Keys"\) allow users to send funds directly to another wallets Ghost Vault. When used in combination with previously Ghosted NIX, full address-less transactions are achieved.

The Pedersen Anonymous Deposits: Commitment Key Packs paper can be found [here](https://nixplatform.io/wp-content/uploads/2018/10/Commitment_Key_Packs_v1-0-1.pdf).

## TOR Anonymity Network

TOR, aka The Onion Router, provides a series of encrypted and randomly changing network relays which makes traffic analysis all but impossible. To outside observers, a person using TOR protects not only their originating IP address, but their destination as well.

Find out more at [https://www.torproject.org](https://www.torproject.org/)

## Dandelion++ Transaction Broadcasting

Using Dandelion++, a transaction first broadcasts to one randomly selected peer using an encrypted connection. This peer then does the same and is repeated until a random number of similar hops has been achieved. This forms what is known as the "stem" phase. The "fluff" phase then activates whereby the transaction is sent to all connected peers in the usual manner, propagating quickly across the entire network.

Detailed information can be found [here](https://arxiv.org/pdf/1805.11060.pdf).

