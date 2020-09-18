---
description: How to import any seed phrase for recovery using Electrum-NIX
---

# Importing Seed Phrases Into Electrum-NIX

Begin by downloading the Electrum-NIX wallet for your Operating System from the [NIX website](https://nixplatform.io/wallet) or directly from [GitHub](https://github.com/NixPlatform/electrum-nix/releases).

Once you've emptied your wallet/sent whatever funds you want to send, you can either keep the wallet for future use \(encryption recommended\), or delete it using File, Delete.

## Flare Wallets \(Mobile and Desktop\)

### Legacy addresses beginning with G

1. Open Electrum-NIX and select File, New/Recover \(or skip to \#2 if you've just installed electrum-nix for the first time\)
2. Give your wallet a name \(Flare Legacy might be an obvious choice\)
3. Select "Standard wallet"
4. Select "I already have a seed"
5. Enter your 12 words and then click on the Options button and select "BIP39 seed"
6. Select "legacy \(p2pkh\)"
7. Be sure the derivation path is: m/44'/400' - For additional accounts in Flare Mobile, add /1' to the end for the 2nd account, /2' for the 3rd, and so on.  Example: m/44'/400'/1' to access your Flare Mobile Legacy NIX wallet in account \#2
8. If you wish to keep this wallet installed as an Electrum account, it is strongly recommended to encrypt it when prompted to do so.

### Segwit addresses beginning with nix1

1. Open Electrum-NIX and select File, New/Recover \(or skip to \#2 if you've just installed electrum-nix for the first time\)
2. Give your wallet a name \(Flare Segwit might be an obvious choice\)
3. Select "Standard wallet"
4. Select "I already have a seed"
5. Enter your 12 words and then click on the Options button and select "BIP39 seed"
6. Select "native segwit \(p2wpkh\)"
7. Be sure the derivation path is: m/84'/400' - For additional accounts in Flare Mobile, add /1' to the end for the 2nd account, /2' for the 3rd, and so on.  Example: m/84'/400'/1' to access your Flare Mobile Segwit NIX wallet in account \#2
8. If you wish to keep this wallet installed as an Electrum account, it is strongly recommended to encrypt it when prompted to do so.

## Webwallet

1. Open Electrum-NIX and select File, New/Recover \(or skip to \#2 if you've just installed electrum-nix for the first time\)
2. Give your wallet a name \(Webwallet might be an obvious choice\)
3. Select "Standard wallet"
4. Select "I already have a seed"
5. Enter your 12 words and then click on the Options button and select "BIP39 seed"
6. Select "legacy \(p2pkh\)"
7. Be sure the derivation path is: m/44'/400'
8. If you wish to keep this wallet installed as an Electrum account, it is strongly recommended to encrypt it when prompted to do so.

## NIX Mobile Wallet

1. Open Electrum-NIX and select File, New/Recover \(or skip to \#2 if you've just installed electrum-nix for the first time\)
2. Give your wallet a name \(Mobile Wallet might be an obvious choice\)
3. Select "Standard wallet"
4. Select "I already have a seed"
5. Enter your 12 words and then click on the Options button and select "BIP39 seed"
6. Select "legacy \(p2pkh\)"
7. Change the derivation path to: m/0'
8. If you wish to keep this wallet installed as an Electrum account, it is strongly recommended to encrypt it when prompted to do so.

