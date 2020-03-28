# Frequently Asked Questions

## How to Fix Staking Issues in QT Wallet

To enable staking, [encrypt your wallet](../wallet-functionality/backup-and-security-1/qt-wallet-encryption.md) and hit unlock for staking under Settings. You should see Staking: with "enabled" in green. To further verify you are in fact staking navigate to the console and type: getstakinginfo and hit enter. You should see a "1" next to staking.

 If you see coins in your available balance but not next to "staked" in the overview tab you may have hit a stake or you may have recently sent a transaction. If staking is enabled you can check your transactions tab and click on the most recent transactions and see how many confirmations they have. Your coins will show up again after 200 confirmations. On the off chance you hit an orphan block or someone finds the same stake just before you, you will likely see a "?" next to the transaction in the transactions tab. The wallet will automatically abandon these transactions for you and return those coins to your staked amount.

 Also remember that only N and nix1 addresses can stake. So if you are running a ghostnode, you will need to manually send those coins from the "G" address to a "N" address and wait the 200 confirmations. You can move your coins around or check which addresses your coins are in via coin control. To enable coin control. Settings &gt; Options &gt; Wallet tab &gt; check Enable Coin Control.

 You can always check the \#info-bot channel in discord by typing !staking 1000 or whatever amount. Just remember this is only an estimate and times can fluctuate wildly as the bot does not take into account coin age or confirmations. 

## How to Fix Wallet Syncing Issues

### Windows: \(always back up wallet.dat first to be safe\)

1. Make sure you are on the latest wallet by checking the version by: help&gt; about nix core. Compare this to github or nixplatform.io version on wallets page.
2. If you are on the latest wallet, close the wallet and in the windows start menu search bar type: %appdata%. If NIX folder does not show click the folder icon on bottom task bar of windows &gt; hit view &gt; and make sure hidden items are checked 
3. Once you find the NIX folder in appdata: delete chainstate folder, blocks folder, banlist.dat, and peers.dat. Then restart wallet and see if you sync up. 

## How to Add Nodes if wallet still will not sync after downloading

1. Go to Help&gt;Debug Window
2. Click on: "Console"
3. In the "search bar" enter the text below, \(Copy and paste it exactly how its written\) after copy pasting press "Enter": addnode ny.nixplatform.io add
4. In the "search bar" enter the text below, \(Copy and paste it exactly how its written\) after copy pasting press "Enter": addnode sf.nixplatform.io add
5. In the "search bar" enter the text below, \(Copy and paste it exactly how its written\) after copy pasting press "Enter": addnode "195.99.60.169:6214" add 
6. In the "search bar" enter the text below, \(Copy and paste it exactly how its written\) after copy pasting press "Enter": addnode "159.65.254.231:6214" add

## How to Import your wallet.dat file

### Windows:

1. Start off by closing your wallet   
2. Open a file explorer and into the file path box  
3. Type or copy-paste: %appdata%\nix\wallets   
4. Extract/Take out the current wallet.dat in the NIX folder \(Place it somewhere safe if you want to save, if not you can delete it. Only delete if no coins are tied to this wallet.dat\).   
5. Import/Insert the wallet.dat file into the NIX folder.   
6. Open/restart your wallet.  
7. DO NOT SHARE YOUR wallet.dat WITH ANYONE. IT CONTAINS YOUR PRIVATE KEYS.



### Mac OS:

1. Start off by closing your wallet. 
2. On the top bar, left side, of your screen click on "Go". Then click on "Go to Folder" 
3. Type or copy-paste: ~/Library/Application Support/nix/ 
4. Export/Extract the current wallet.dat in the NIX folder \(Place it somewhere safe if you want to save, if not you can delete it. Only delete if no coins are tied to this wallet.dat\). 
5. Import/Insert the wallet.dat file into the NIX folder. 
6. Open/restart your wallet.
7. DO NOT SHARE YOUR wallet.dat with ANYONE. IT CONTAINS YOUR PRIVATE KEYS.



### Linux:

1. Start off by closing your wallet.  
2. Open a file explorer and into the file path box.  
3. Type or copy-paste: $HOME/.nix/wallets.  
4. Extract/Take out the current wallet.dat in the NIX folder \(Place it somewhere safe if you want to save, if not you can delete it. Only delete if no coins are tied to this wallet.dat\).  
5. Import/Insert the wallet.dat file into the NIX folder.  
6. Open/restart your wallet.  
7. DO NOT SHARE YOUR wallet.dat WITH ANYONE. IT CONTAINS YOUR PRIVATE KEYS.

## How to Get your Private Keys

If your NIX wallet is encrypted, to get your private key for a certain NIX address please follow the steps: \(if your wallet is not encrypted ignore step \#3\) \(Don't enter the "" in any of the steps, they are used to show the input\).

1. Go to: Help&gt;"Debug Window"  
2. Click on: "Console"  
3. In the "search bar" enter: walletpassphrase "Passphrase for your NIX wallet" "60" - "Passphrase for your NIX wallet" = Passphrase that you entered to encrypt your wallet. - "60" = the seconds you want to unlock.  
4. In the same "search bar" enter: dumpprivkey "NIX address" - "NIX address" = address that you want to access the private key to.

 DO NOT SHARE YOUR PRIVATE KEYS WITH ANYONE

## What to do if your Transaction Does Not Send

Make sure you are using the most up to date wallet. If you are not, then upgrade and this should fix it. If you are on the latest wallet and it still will not send. Go to Help&gt;Debug Window&gt;Console&gt; type: resendwallettransactions then hit Enter.

## What to do if your Coins are Missing after Updating your Wallet

Once wallet is fully synced click on the transactions tab. Look for any transactions that have a "?" next to them. If you see any right click and select abandon. They should show back up. Sometimes your coins may just be missing because you hit a stake reward. They will automatically show back up after 200 confirmations. 

## How to Check Amount on Confirmations on a TX

In the transactions tab, just click on the transaction and it will show the amount of confirmations.

## How to Check and Update Ghostnode and Troubleshooting

Log into the vps via putty \(windows\) or terminal \(unix\) and run these commands:

nix-cli getnetworkinfo - check vps version near the top. If it doesn't match and you used cryptosharks auto-installer \(most likely\) you need to use his auto-updater here: [https://github.com/cryptosharks131/Ghostnode\#updating](https://github.com/cryptosharks131/Ghostnode#updating) - paste the 3 lines in and press enter 

nix-cli getblockchaininfo - check vps block height near the top \(should match [https://blockchain.nixplatform.io/](https://blockchain.nixplatform.io/)\) If it doesn't match then you need to follow dacx's bootstrap pinned to \#wallets in discord. First stop the NIX service by pasting into the vps: systemctl stop NIX To get the bootstrap files onto your VPS you can use something like FileZilla from your local machine. Install but untick the bloatware on install, you don't need these. Log into your vps via FileZilla using same credentials as putty/terminal in the quick connect section and use Port 22. Navigate to the nix folder and remove the items in dacx's bootstrap guide. Unzip the files you downloaded on the guide link, and drag into the Nix folder on the filezilla session. Now go back to putty/terminal and start the service again with systemctl start NIX. Check height in putty/terminal again against block explorer height with nix-cli getblockchaininfo If that checks out and matches you're good to go. Close and re-open your local wallet, go to ghostnodes &gt; start all. They should move to PRE-ENABLED and move to ENABLED in 20mins or so. 

PS - while you're logged into VPS via putty/terminal, best to update the server packages. paste this command to update/upgrade: apt-get update && apt-get upgrade



