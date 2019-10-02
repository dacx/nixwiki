# Usage Guide

A list of all possible commands can be found by executing `nix-cli help` or viewing them on the Console Commands page.

{% page-ref page="../advanced-wallet-functions/console-commands.md" %}

The `command` method takes a list of parameters and returns the response. For example, this would be a valid way to ghost \(and un-ghost\) 0.1 NIX and log the response to the console:

```text
//ghost 0.1 NIX and log response
client.command('ghostamountv2', '0.1').then(value => console.log(value)); 

//un-ghost 0.1 NIX and log response
client.command('unghostamountv2', '0.1').then(value => console.log(value)); 
```

Here is a list of the most popular commands. Legend: `<required_value>`, `[optional_value]`

| Command | Effect |
| :--- | :--- |
| ghostamountv2 &lt;amount&gt; \[address\] | Ghost &lt;amount&gt; NIX \[to external CKP\].  |
| unghostamountv2 &lt;amount&gt; \[address\] | Un-ghost &lt;amount&gt; NIX \[to external address or CKP\]. |
| getpubcoinpackv2 | Get a commitment key pack \(CKP\) for 2-Way-Ghosting. |
| getblockchaininfo | Get the current blockchain statistics. |
| getstakinginfo | Get the current staking statistics. |
| sendfrom &lt;from&gt; &lt;to&gt; &lt;amount&gt; | Sends &lt;amount&gt; NIX &lt;from account&gt; &lt;to address&gt;. |
| sendtoaddress &lt;address&gt; &lt;amount&gt; | Sends &lt;amount&gt; NIX to &lt;address&gt;. |
| getbalance \[account\] | Get balance for entire wallet or only one \[account\]. |

Please note that you can always execute `help <command_name>` for a more detailed explanation of the commands:

![help getaddressbalance](../.gitbook/assets/help-getaddressbalance.png)

