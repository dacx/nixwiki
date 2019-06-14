# Syncing Issues

{% hint style="warning" %}
Should for whatever reason the following doesn't fix your issue, join the [Discord server](https://discord.gg/HGuvDTW) and ask in the **public channels only** for help. **Do not respond to any DMs** as scammers might try to trick you into giving them your funds!
{% endhint %}

If you happen to be on the wrong chain due to not updating your wallet in time, this will get you back on track.

1. Verify that you are indeed on the wrong chain by comparing your block height to the [explorer](https://blockchain.nixplatform.io/).
2. Update your wallet to the latest by downloading it from [GitHub](https://github.com/NixPlatform/NixCore/releases) \(don't start the wallet yet\).
3. Navigate to the NIX data directory \(see the OS dependent steps below\). 
4. Create a backup of your wallet.dat \(either located on the root of the data dir or in /wallets\) to be on the safe side.
5. Delete the following from the data dir:
   1. blocks \(entire directory\)
   2. chainstate \(entire directory\)
   3. banlist.dat
   4. peers.dat
6. Start the new wallet. Wait for the wallet to finish syncing and you're good to go!

### Finding the NIX data directory

#### Windows

1. Hit Windows Key + R.
2. Type `%appdata%` and hit Enter.
3. Click on the `roaming` directory.
4. Click on the `nix` directory.

#### Linux

1. The data dir is located in `~./nix` .

#### Mac OS

1. In the Top Bar locate and click `Go -> Go to Folder` .
2. Paste `~/Library/Application Support/nix/` and hit Enter.

