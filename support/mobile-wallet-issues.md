---
description: Common mobile wallet issues
---

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

If you cannot seem to get your wallet to work for any reason, you can always import your seed into Electrum-NIX by using the following guide:

{% page-ref page="importing-seed-phrases-into-electrum-nix.md" %}

