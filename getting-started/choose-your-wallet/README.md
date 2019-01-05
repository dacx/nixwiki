# Overview of NIX Wallets

## Available Wallets

The following wallets are currently available for download; QT, UI, Electrum, SPV Mobile and CLI. 

The QT and UI wallets are both based on NIX Core meaning they share the same daemon and wallet.dat \(if the default installation directory is preserved\) whereas the Electrum and SPV wallets are separate entities. 

This means you can have both the QT and UI wallets installed on the same machine giving the user access to the slick UI interface for every day tasks as well as the fully featured QT wallet as needed. For a comparison see:

{% page-ref page="wallet-comparison.md" %}

## QT Wallet

The QT wallet is the one most crypto currency user have seen before. Clean interface with a focus on functionality rather than design.

![NIX Core QT wallet](../../.gitbook/assets/nix-core-wallet-_005.png)

**Recommended for:** everyone

**Download:** [https://github.com/NixPlatform/NixCore/releases](https://github.com/NixPlatform/NixCore/releases)

## GUI Wallet

True eye-candy. With a focus on user experience, the GUI wallet is perfect for users that prefer a visually pleasing interface and do not use more in-depth functionalities.

![NIX UI Wallet](../../.gitbook/assets/image%20%282%29.png)

**Recommended for:** new users, UX enthusiasts

**Download:** [https://github.com/NixPlatform/Nix-GUI/releases](https://github.com/NixPlatform/Nix-GUI/releases)

## Electrum Wallet

A light weight wallet that supports only the basic functionalities and also runs on mobile devices. It features seed recovery and 2FA.

![NIX Electrum Wallet](../../.gitbook/assets/image%20%286%29.png)

**Recommended for:** everyone

**Download:** [https://github.com/NixPlatform/electrum-nix/releases](https://github.com/NixPlatform/electrum-nix/releases)

## SPV Mobile Wallets

Available for both Android and iOS, our mobile wallets have just been released. This is the most secure way to have access to your NIX on the go. 

![](../../.gitbook/assets/image%20%283%29.png)

​**Recommended for:** mobile users

**Download:** Available on the Google Play Store and TestFight by invitation. Alternatively you can build the wallets directly from here:  
[https://github.com/NixPlatform/nixwallet-spv-android](https://github.com/NixPlatform/nixwallet-spv-android)  
[https://github.com/NixPlatform/nixwallet-spv-ios](https://github.com/NixPlatform/nixwallet-spv-ios)

## CLI Wallet \(command line interface\)

The command line tool for all those that need it. View all available commands by typing the following while having **nixd** running:

```text
$ ./nix-cli help
```

**Recommended for:** experts, developers, debugging

**Download:** [https://github.com/NixPlatform/NixCore/releases](https://github.com/NixPlatform/NixCore/releases)

