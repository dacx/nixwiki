# Ghost Vault

The NIX Ghost Vault became available for use at block \#53,000 using the Zerocoin Protocol. As of block \#232,000, the Zerocoin Protocol was actively replaced with Sigma which significantly reduces on-chain proof sizes from 25kb to 1.5kb, reduces Commitment Key Pack lengths by 73%, and significantly increases anonymity sets by introducing 256-bit elliptic curves which would be roughly equivalent to 3072-bit RSA as opposed to 2048-bit RSA previously used in the Zerocoin Protocol. Massive credit goes to the [ZCoin](https://zcoin.io) development team for creating the [first Sigma cryptographic codebase implementation](https://twitter.com/zcoinofficial/status/1118819578472206337) and their developments on these grounds.

The NIX Ghost Vault provides privacy for the sender and/or the receiver by essentially burning coins and allowing users to re-issue them later with no attached transaction history. The Ghost Vault can be utilized in 4 ways:

**Holder Privacy \(1-Way Ghosting\)**  
By ghosting your public NIX into your Ghost Vault, an outside observer has no proof that your wallet still possess those coins.

**Sender Privacy \(1-Way Ghosting\)**  
By sending your previously ghosted NIX to a receivers public address, the recipient receives newly minted public coins with no attached history.

**Receiver Privacy \(1-Way Ghosting\)**  
For receiver-only privacy, you can ghost your public NIX directly into the recipients Ghost Vault.

**Sender and Receiver Privacy \(2-Way Ghosting\)**  
Sending your previously ghosted NIX from your Ghost Vault to the recipients Ghost Vault results in a full public address-less transaction.

