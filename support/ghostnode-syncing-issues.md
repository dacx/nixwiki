# Ghostnode Syncing Issues

**Script Installs, e.g. CryptoSharks method:**

```text
systemctl stop NIX
rm -r ~/.nix/{blocks,chainstate,peers.dat,banlist.dat}
systemctl start NIX
```

 **Manual Installs:**

```text
nix-cli stop
rm -r ~/.nix/{blocks,chainstate,peers.dat,banlist.dat}
nixd &
```



{% hint style="warning" %}
Should for whatever reason the following doesn't fix your issue, join the [Discord server](https://discordapp.com/invite/HGuvDTW) and ask in the **public channels only** for help. **Do not respond to any DMs** as scammers might try to trick you into giving them your funds!
{% endhint %}

