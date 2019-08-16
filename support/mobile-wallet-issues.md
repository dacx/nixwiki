# Mobile Wallet Issues

## Funds Aren't Showing Up

If some/all of your funds aren't showing up \(typically after importing/recovering your seed phrase from an older/other device\), chances are good your wallet is not sync'd.

**Easy things to try first:**

1. Close and re-open the app.
2. Reboot the device.
3. If using WiFi, disable it and try using your cellular data connection.

**Force the wallet to re-sync:**

1. Menu
2. Settings
3. Sync Blockchain
4. Start Sync

**If you are still unable to properly re-sync, try:**

1. Menu
2. Settings
3. Advanced
4. NIX Nodes
5. Switch to Manual Mode

Here, it will ask you for an IP address. An easy way to get one is from a block explorer such as [https://chainz.cryptoid.info/nix/\#!network](https://chainz.cryptoid.info/nix/#!network). Find a latest version node and click on the "node list" button. You may need to attempt a re-sync once again.

Once sync'd and you've completed any sends you want to do, you will probably want to get back to the NIX Nodes section and switch back to Automatic Mode, as there is no guarantee the node you manually added will remain online forever.

## How Import Your Mobile Seed Phrase into Electrum-NIX

If for whatever reason you are unable to get your mobile wallet to work properly, or perhaps your device is destroyed/lost/stolen and you want to use the funds but don't yet have another device to restore to, you can easily import your seed phrase into an electrum-nix desktop wallet.

Begin by downloading the electrum-nix wallet for your Operating System from the [NIX website](https://nixplatform.io/wallet) or directly from [GitHub](https://github.com/NixPlatform/electrum-nix/releases). After you've installed it, open it and:

1. Select File, New/Recover \(or skip to \#2 if you've just installed electrum-nix for the first time\)
2. Give your wallet a name \(Mobile Wallet might be an obvious choice\)
3. Select "Standard wallet"
4. Select "I already have a seed"
5. Enter your 12 words and then click on the Options button and select "BIP39 seed"
6. Select "legacy \(p2pkh\)"
7. Change the derivation path to: m/0'
8. If you wish to keep this wallet installed, you should probably encrypt it when prompted to do so.

You will now have access to your SPV wallet using electrum-nix. From here, you can send them anywhere you like.

Once you've emptied your wallet/sent whatever funds you want to send, you can either keep the wallet for future use \(encryption recommended\), or delete it using File, Delete.

