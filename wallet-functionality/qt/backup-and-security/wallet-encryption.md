---
description: How to encrypt your QT wallet
---

# Wallet Encryption

Encrypting your wallet.dat file will require that you enter a password in order to send any NIX. It is also a requirement if you wish to stake your NIX directly from your own wallet. 

Although you can perform this action at any time, it is recommended that you do it immediately upon starting a new nix-qt wallet and before generating/using any receive addresses. Encrypting your wallet.dat file also changes your master seed, so any backups you created before encryption **WILL NOT** backup addresses you've created/generated after encryption.

From the Settings menu, select "Encrypt Wallet..." to begin the process of encrypting your wallet.dat file.

![Select &quot;Encrypt Wallet...&quot; from the Settings menu](../../../.gitbook/assets/qt-encryptmenu.png)

![Choose a very strong passphrase](../../../.gitbook/assets/qt-encryptwindow.png)

![Confirm that you wish to encrypt your wallet](../../../.gitbook/assets/qt-confirmencryption.png)

{% hint style="info" %}
**NOTE:** After confirming you wish to encrypt your wallet, it may take a few moments to apply the encryption.
{% endhint %}

![](../../../.gitbook/assets/qt-encrypteddialog.png)

Clicking OK on the final dialog box will close the wallet. The next time you open it you will be required to use your passphrase in order to send or stake your NIX, so do not lose it!

## Changing the QT Wallet passphrase

Once your wallet is encrypted, you can later change the passphrase if you wish. From the Settings menu, select "Change Passphrase..." 

Make sure to replace your old wallet backups with the new one.

![Select &quot;Change Passphrase...&quot; from the Settings menu](../../../.gitbook/assets/qt-changepwmenu.png)

![Fill in your current passphrase and choose a new one](../../../.gitbook/assets/qt-changepw.png)





