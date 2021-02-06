# Console Commands

This is a list of all available commands in the NIX Core, usable in the nix-qt wallet debug console, UI console, and the nix-cli command line interface.

## NIX Ghostnode

`getpoolinfo` Returns an object containing mixing pool related information

`ghostnode "command"...` Set of commands to execute ghostnode related actions.  
  
**Arguments:**  
1. "command" \(string or set of strings, required\) The command to execute,  
  
**Available commands:**

* `count` Print number of all known ghostnodes \(optional: 'ps', 'enabled', 'all', qualify'\)
* `current` Print info on current ghostnode winner to be paid the next block \(calculated locally\)
* `debug` Print ghostnode status
* `genkey` Generate new ghostnodeprivkey
* `outputs` Print ghostnode compatible outputs
* `start` Start local Hot ghostnode configured in nix.conf
* `start-alias` Start single remote ghostnode by assigned alias configured in ghostnode.conf
* `start-<mode>` Start remote ghostnodes configured in ghostnode.conf \(&lt;mode&gt;: 'all', 'missing', 'disabled'\)
* `status` Print ghostnode status information
* `list` Print list of all known ghostnodes \(see ghostnodelist for more info\)
* `list-conf` Print ghostnode.conf in JSON format
* `winner` Print info on the next ghostnode winner to vote for
* `winners` print list of ghostnode winners

`ghostnodebroadcast "command"...` Set of commands to create and relay ghostnode broadcast messages  
  
**Arguments:**  
1. "command" \(string or set of strings, required\) The command to execute  
  
**Available commands:**

* `create-alias` - Create single remote ghostnode broadcast message by assigned alias configured in ghostnode.conf
* `create-all` - Create remote ghostnode broadcast messages for all ghostnodes configured in ghostnode.conf
* `decode` - Decode ghostnode broadcast message
* `relay` - Relay ghostnode broadcast message to the network

`ghostnodebroadcast "command"...` Set of commands to create and relay ghostnode broadcast messages.  
  
**Arguments:**  
1. "command" \(string or set of strings, required\) The command to execute

**Available commands:**

`ghostnodelist ("mode" "filter")` Get a list of ghostnodes in different modes  
  
**Arguments:**  
1. "mode" \(string, optional/required to use filter, default = status\) The mode to run list in  
2. "filter" \(string, optional\) Filter results. Partial match by outpoint by default in all modes, additional matches in some modes are also available  
  
**Available modes:**

* `activeseconds` Print number of seconds ghostnode recognized by the network as enabled \(since latest issued "ghostnode start/start-many/start-alias"\)
* `addr` Print ip address associated with a ghostnode \(can be additionally filtered, partial match\)
* `full` Print info in format 'status protocol payee lastseen activeseconds lastpaidtime lastpaidblock IP' \(can be additionally filtered, partial match\)
* `lastpaidblock` Print the last block height a node was paid on the network
* `lastpaidtime` Print the last time a node was paid on the network
* `lastseen` Print timestamp of when a ghostnode was last seen on the network
* `payee` Print NIX address associated with a ghostnode \(can be additionally filtere, partial match\)
* `protocol` Print protocol of a ghostnode \(can be additionally filtered, exact match\)
* `rank` Print rank of a ghostnode based on current block
* `quialify` Print qualify status of a ghostnode based on current block
* `status` Print ghostnode status: PRE\_ENABLED / ENABLED /EXPIRED /WATCHDOG\_EXPIRED / NEW\_START\_REQUIRED / UPDATE\_REQUIRED / POSE\_BAN / OUTPOINT\_SPENT \(can be additionally filtered, partial match
* `create-alias` Create single remote ghostnode broadcast message by assigned alias configured in ghostnode.conf
* `create-all` Create remote ghostnode broadcast messages for all ghostnodes configured in ghostnode.conf
* `decode` Decode ghostnode broadcast message
* `relay` Relay ghostnode broadcast message to the network

`ghostsync [status|next|reset]` Returns the sync status, updates to the next step or resets it entirely

## NIX Governance

`eraseallgoventires` Erase all wallet database voting entries for the current local wallet.  
Requires wallet passphrase to be set with walletpassphrase call.

`getaddressvoteweight` Returns vote weight for an address \(requires addressindex to be enabled\).  
  
**Arguments:**  
{  
  "addresses"  
    \[  
      "address" \(string\) The base58check encoded address  
    ,...  
    \]  
  "start" \(number\) The start time of the vote weight period  
  "end" \(number\) The end time of the vote weight period  
}  
  
**Result:**  
\[  
  {  
    "voteweight" \(number\) The vote weight of the address  
  }  
\]  
  
**Examples:**  
&gt; nix-cli getaddressvoteweight '{"addresses": \["NwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\], "start": 10, "end": 20}'  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getaddressvoteweight", "params": \['{"addresses": \["NwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}'\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getoffchainproposals` Returns a list of all proposals.

`getproposaltimeframeinfo` Returns total weight a proposal in a given timeframe can possibly have.  
  
**Arguments:**  
{  
  "start" \(number\) The start time of the vote weight period  
  "end" \(number\) The end time of the vote weight period  
}  
  
**Result:**  
\[  
  {  
    "total\_possible\_votes" \(number\) The total possible weight of the timeframe  
  }  
\]  
  
**Examples:**  
&gt; nix-cli getproposaltimeframeinfo '{"start": 1559229685, "end": 1569229685}'

`getvoteweight start_time end_time` Requires wallet passphrase to be set with walletpassphrase call.  
  
**Arguments:**  
1. "start\_time" \(int, required\) The starting time \(unix\) for the weight calculation.  
2. "end\_time" \(int, required\) The ending time \(unix\) for the weight calculation.

## NIX Privacy

`decryptallzerocoins` Decrypt all encrypted zerocoin data

`enabletor <enable>(false/true)` To enable obfuscation, set enabletor to "true".  
Please restart the NIX daemon to update your changes

`encryptallzerocoins` Encrypts all zerocoin data

`eraseunusedzerocoindata` Erases zerocoin metadata from spent zerocoins

`getzerocoinacc` 

`getpubcoinpack amount(default=10)` Results a Commitment Key Pack

`getpubcoinpackv2 amount(default=10)` Results a Commitment Key Pack

`getsigmaseed` Dump the deterministic sigma seed for all sigma coins.  
Requires wallet passphrase to be set with walletpassphrase call.  
  
**Result**  
"seed" : s, \(string\) The deterministic zPIV seed.  
  
**Examples**  
&gt; nix-cli getsigmaseed  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getsigmaseed", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getzerocoinacc`

`ghostamount <amount>(whole numbers only) <commitment key pack>` Requires wallet passphrase to be set with walletpassphrase call.

`ghostamountv2 <amount>(whole numbers only) <commitment_key_pack>(optional)` Requires wallet passphrase to be set with walletpassphrase call.

`ghostfeepayouttotal` Get the ghostfee payout total in the upcoming cycle.

`ghostprivacysets` Get the total ghosted denomination amounts in the network.

`ghostprivacysetsv2` Get the total ghosted denomination amounts in the network.

`listallserials height(default=current_height)` Lists all zerocoin serials spent from height

`listpubcoin <all>(1/5/10/50/100/500/1000/5000)`   
  
**Arguments:**  
1. &lt;all&gt; \(int, optional\) 1,5,10,50,100,500,1000,5000 \(default\) to return all pubcoin with denomination. empty to return all pubcoin.

**Results are an array of Objects, each of which has:**  
{id, IsUsed, denomination, value, serialNumber, nHeight, randomness}

`listsigmaentries <true/false>(default = false)` List sigma entries in wallet.  
Requires wallet passphrase to be set with walletpassphrase call.  
  
**Arguments:**  
1. &lt;true/false&gt; \(string, required\) Whether to list all entries including spent.

`listunloadedpubcoins amount(default=all)` Results are an array of public ghost keys

`listunspentghostednix [minconf=1] [maxconf=9999999]`   
Returns array of unspent transaction outputs with between minconf and maxconf \(inclusive\) confirmations.  
  
**Results are an array of Objects, each of which has:**  
{txid, vout, scriptPubKey, amount, confirmations}

`mintghostdata <amount>(1,5,10,50,100,500,1000,5000)`

`payunloadedpubcoins`   
  
**Arguments:**  
Amount to pay  
Ghost key string:

`refillghostkeys <amount>(default=100)` Requires wallet passphrase to be set with walletpassphrase call.

`resetmintzerocoin` Requires wallet passphrase to be set with walletpassphrase call.

`resetzerocoinamounts` Erases unconfirmed zerocoins

`resetzerocoinunconfirmed` Erases unconfirmed zerocoins

`setsigmaseed "seed"` Set the wallet's deterministic sigma seed to a specific value.  
Requires wallet passphrase to be set with walletpassphrase call.  
  
**Arguments:**  
1. "seed" \(string, required\) The deterministic sigma seed.  
  
**Result**  
"success" : b, \(boolean\) Whether the seed was successfully set.  
  
**Examples**  
&gt; nix-cli setsigmaseed 6b54736b13ce6990753b7345a9b41ca2ce5c5847125b49bf3ffa15f47f5001cd  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "setsigmaseed", "params": \[6b54736b13ce6990753b7345a9b41ca2ce5c5847125b49bf3ffa15f47f5001cd\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`spendghostdata <amount>(1,5,10,50,100,500,1000,5000), <seckey>, <randomness>, <serial>, <pubValue>, <spendtoaddress>` 

`torstatus` Returns the status of tor obfuscation on your NIX daemon

`unghostamount <amount>(whole numbers only) <addresstosend>(either address or commitment key pack)` Requires wallet passphrase to be set with walletpassphrase call.

`unghostamountv2 <amount>(whole numbers only) <addresstosend>(either address or commitment key pack)` Requires wallet passphrase to be set with walletpassphrase call.

## Address Index

`getaddressbalance` Returns the balance for an address\(es\) \(requires addressindex to be enabled\).  
  
**Arguments:**  
{  
  "addresses"  
    \[  
      "address" \(string\) The base58check encoded address  
      ,...  
    \]  
}  
  
**Result:**  
{  
  "balance" \(string\) The current balance in nix  
  "received" \(string\) The total number of nix received \(including change\)  
}  
  
**Examples:**  
&gt; nix-cli getaddressbalance '{"addresses": \["XwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}'  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getaddressbalance", "params": \[{"addresses": \["XwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getaddressdeltas` Returns all changes for an address \(requires addressindex to be enabled\).  
  
**Arguments:**  
{  
  "addresses"  
    \[  
      "address" \(string\) The base58check encoded address  
      ,...  
    \]  
  "start" \(number\) The start block height  
  "end" \(number\) The end block height  
}  
  
**Result:**  
\[  
  {  
    "satoshis" \(number\) The difference of nix  
    "txid" \(string\) The related txid  
    "index" \(number\) The related input or output index  
    "blockindex" \(number\) The related block index  
    "height" \(number\) The block height  
    "address" \(string\) The base58check encoded address  
  }  
\]  
  
**Examples:**  
&gt; nix-cli getaddressdeltas '{"addresses": \["NwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}'  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getaddressdeltas", "params": \[{"addresses": \["NwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getaddressmempool` Returns all mempool deltas for an address \(requires addressindex to be enabled\).  
  
**Arguments:**  
{  
  "addresses"  
    \[  
      "address" \(string\) The base58check encoded address  
      ,...  
    \]  
}  
  
**Result:**  
\[  
  {  
    "address" \(string\) The base58check encoded address  
    "txid" \(string\) The related txid  
    "index" \(number\) The related input or output index  
    "satoshis" \(number\) The difference of nix  
    "timestamp" \(number\) The time the transaction entered the mempool \(seconds\)  
    "prevtxid" \(string\) The previous txid \(if spending\)  
    "prevout" \(string\) The previous transaction output index \(if spending\)  
  }  
\]  
  
**Examples:**  
&gt; nix-cli getaddressmempool '{"addresses": \["NwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}'  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getaddressmempool", "params": \[{"addresses": \["NwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getaddresstxids` Returns the txids for an address\(es\) \(requires addressindex to be enabled\).  
  
**Arguments:**  
{  
  "addresses"  
    \[  
      "address" \(string\) The base58check encoded address  
      ,...  
    \]  
  "start" \(number\) The start block height  
  "end" \(number\) The end block height  
}  
  
**Result:**  
\[  
  "transactionid" \(string\) The transaction id  
  ,...  
\]  
  
**Examples:**  
&gt; nix-cli getaddresstxids '{"addresses": \["XwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}'  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getaddresstxids", "params": \[{"addresses": \["XwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getaddressutxos` Returns all unspent outputs for an address \(requires addressindex to be enabled\).  
  
**Arguments:**  
{  
  "addresses"  
    \[  
      "address" \(string\) The base58check encoded address  
      ,...  
    \]  
}  
  
**Result:**  
\[  
  {  
  "address" \(string\) The address base58check encoded  
  "txid" \(string\) The output txid  
  "outputIndex" \(number\) The output index  
  "script" \(string\) The script hex encoded  
  "satoshis" \(number\) The number of nix of the output  
  "height" \(number\) The block height  
  }  
\]  
  
**Examples:**  
&gt; nix-cli getaddressutxos '{"addresses": \["NwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}'  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getaddressutxos", "params": \[{"addresses": \["NwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

## Blockchain

`getbestblockhash` Returns the hash of the best \(tip\) block in the longest blockchain.  
  
**Result:**  
"hex" \(string\) the block hash hex encoded  
  
**Examples:**  
&gt; nix-cli getbestblockhash  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getbestblockhash", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getblock "blockhash" (verbosity)`  
If verbosity is 0, returns a string that is serialized, hex-encoded data for block 'hash'.  
If verbosity is 1, returns an Object with information about block &lt;hash&gt;.  
If verbosity is 2, returns an Object with information about block &lt;hash&gt; and information about each transaction.  
  
**Arguments:**  
1. "blockhash" \(string, required\) The block hash  
2. verbosity \(numeric, optional, default=1\) 0 for hex encoded data, 1 for a json object, and 2 for json object with transaction data  
  
**Result \(for verbosity = 0\):**  
"data" \(string\) A string that is serialized, hex-encoded data for block 'hash'.  
  
**Result \(for verbosity = 1\):**  
{  
  "hash" : "hash", \(string\) the block hash \(same as provided\)  
  "confirmations" : n, \(numeric\) The number of confirmations, or -1 if the block is not on the main chain  
  "size" : n, \(numeric\) The block size  
  "strippedsize" : n, \(numeric\) The block size excluding witness data  
  "weight" : n \(numeric\) The block weight as defined in BIP 141  
  "height" : n, \(numeric\) The block height or index  
  "version" : n, \(numeric\) The block version  
  "versionHex" : "00000000", \(string\) The block version formatted in hexadecimal  
  "merkleroot" : "xxxx", \(string\) The merkle root  
  "tx" : \[ \(array of string\) The transaction ids  
  "transactionid" \(string\) The transaction id  
    \[  
      ,...  
    \],  
  "time" : ttt, \(numeric\) The block time in seconds since epoch \(Jan 1 1970 GMT\)  
  "mediantime" : ttt, \(numeric\) The median block time in seconds since epoch \(Jan 1 1970 GMT\)  
  "nonce" : n, \(numeric\) The nonce  
  "bits" : "1d00ffff", \(string\) The bits  
  "difficulty" : x.xxx, \(numeric\) The difficulty  
  "chainwork" : "xxxx", \(string\) Expected number of hashes required to produce the chain up to this block \(in hex\)  
  "previousblockhash" : "hash", \(string\) The hash of the previous block  
  "nextblockhash" : "hash" \(string\) The hash of the next block  
}  
  
**Result \(for verbosity = 2\):**  
{  
  ..., Same output as verbosity = 1.  
  "tx" : \[ \(array of Objects\) The transactions in the format of the getrawtransaction RPC. Different from verbosity = 1 "tx" result.  
    \[  
      ,...  
    \],  
  ,... Same output as verbosity = 1.  
}  
  
**Examples:**  
&gt; nix-cli getblock "00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblock", "params": \["00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  


`getblockchaininfo` Returns an object containing various state info regarding blockchain processing.  
  
**Result:**  
{  
  "chain": "xxxx", \(string\) current network name as defined in BIP70 \(main, test, regtest\)  
  "blocks": xxxxxx, \(numeric\) the current number of blocks processed in the server  
  "headers": xxxxxx, \(numeric\) the current number of headers we have validated  
  "bestblockhash": "...", \(string\) the hash of the currently best block  
  "difficulty": xxxxxx, \(numeric\) the current difficulty  
  "mediantime": xxxxxx, \(numeric\) median time for the current best block  
  "verificationprogress": xxxx, \(numeric\) estimate of verification progress \[0..1\]  
  "initialblockdownload": xxxx, \(bool\) \(debug information\) estimate of whether this node is in Initial Block Download mode.  
  "chainwork": "xxxx" \(string\) total amount of work in active chain, in hexadecimal  
  "size\_on\_disk": xxxxxx, \(numeric\) the estimated size of the block and undo files on disk  
  "pruned": xx, \(boolean\) if the blocks are subject to pruning  
  "pruneheight": xxxxxx, \(numeric\) lowest-height complete block stored \(only present if pruning is enabled\)  
  "automatic\_pruning": xx, \(boolean\) whether automatic pruning is enabled \(only present if pruning is enabled\)  
  "prune\_target\_size": xxxxxx, \(numeric\) the target size used by pruning \(only present if automatic pruning is enabled\)  
  "softforks": \[ \(array\) status of softforks in progress  
    {  
      "id": "xxxx", \(string\) name of softfork  
      "version": xx, \(numeric\) block version  
      "reject": { \(object\) progress toward rejecting pre-softfork blocks  
      "status": xx, \(boolean\) true if threshold reached  
    },  
  }, ...  
\],  
  "bip9\_softforks": { \(object\) status of BIP9 softforks in progress  
  "xxxx" : { \(string\) name of the softfork  
  "status": "xxxx", \(string\) one of "defined", "started", "locked\_in", "active", "failed"  
  "bit": xx, \(numeric\) the bit \(0-28\) in the block version field used to signal this softfork \(only for "started" status\)  
  "startTime": xx, \(numeric\) the minimum median time past of a block at which the bit gains its meaning  
  "timeout": xx, \(numeric\) the median time past of a block at which the deployment is considered failed if not yet locked in  
  "since": xx, \(numeric\) height of the first block to which the status applies  
  "statistics": { \(object\) numeric statistics about BIP9 signalling for a softfork \(only for "started" status\)  
  "period": xx, \(numeric\) the length in blocks of the BIP9 signalling period  
  "threshold": xx, \(numeric\) the number of blocks with the version bit set required to activate the feature  
  "elapsed": xx, \(numeric\) the number of blocks elapsed since the beginning of the current period  
  "count": xx, \(numeric\) the number of blocks with the version bit set in the current period  
  "possible": xx \(boolean\) returns false if there are not enough blocks left in this period to pass activation threshold  
  }  
 }  
}  
  "warnings" : "...", \(string\) any network and blockchain warnings  
}  
  
**Examples:**  
&gt; nix-cli getblockchaininfo  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblockchaininfo", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getblockcount` Returns the number of blocks in the longest blockchain.  
  
**Result:**  
n \(numeric\) The current block count  
  
**Examples:**  
&gt; nix-cli getblockcount  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblockcount", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getblockhash <height>` Returns hash of block in best-block-chain at height provided.  
  
**Arguments:**  
1. height \(numeric, required\) The height index  
  
**Result:**  
"hash" \(string\) The block hash  
  
**Examples:**  
&gt; nix-cli getblockhash 1000  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblockhash", "params": \[1000\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getblockhashes <timestamp timestamp>` Returns array of hashes of blocks within the timestamp range provided.  
  
**Arguments:**  
1. high \(numeric, required\) The newer block timestamp  
2. low \(numeric, required\) The older block timestamp  
  
**Result:**  
\[  
  "hash" \(string\) The block hash  
\]  
  
**Examples:**  
&gt; nix-cli getblockhashes 1231614698 1231024505  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblockhashes", "params": \[1231614698, 1231024505\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getblockheader "hash" (verbose)` If verbose is false, returns a string that is serialized, hex-encoded data for blockheader 'hash'. If verbose is true, returns an Object with information about blockheader &lt;hash&gt;.  
  
**Arguments:**  
1. "hash" \(string, required\) The block hash  
2. verbose \(boolean, optional, default=true\) true for a json object, false for the hex encoded data  
  
**Result \(for verbose = true\):**  
{  
  "hash" : "hash", \(string\) the block hash \(same as provided\)  
  "confirmations" : n, \(numeric\) The number of confirmations, or -1 if the block is not on the main chain  
  "height" : n, \(numeric\) The block height or index  
  "version" : n, \(numeric\) The block version  
  "versionHex" : "00000000", \(string\) The block version formatted in hexadecimal  
  "merkleroot" : "xxxx", \(string\) The merkle root  
  "time" : ttt, \(numeric\) The block time in seconds since epoch \(Jan 1 1970 GMT\)  
  "mediantime" : ttt, \(numeric\) The median block time in seconds since epoch \(Jan 1 1970 GMT\)  
  "nonce" : n, \(numeric\) The nonce  
  "bits" : "1d00ffff", \(string\) The bits  
  "difficulty" : x.xxx, \(numeric\) The difficulty  
  "chainwork" : "0000...1f3" \(string\) Expected number of hashes required to produce the current chain \(in hex\)  
  "previousblockhash" : "hash", \(string\) The hash of the previous block  
  "nextblockhash" : "hash", \(string\) The hash of the next block  
}  
  
**Result \(for verbose=false\):**  
"data" \(string\) A string that is serialized, hex-encoded data for block 'hash'.  
  
**Examples:**  
&gt; nix-cli getblockheader "00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblockheader", "params": \["00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getchaintips` Return information about all known tips in the block tree, including the main chain as well as orphaned branches.  
  
**Result:**  
\[  
  {  
    "height": xxxx, \(numeric\) height of the chain tip  
    "hash": "xxxx", \(string\) block hash of the tip  
    "branchlen": 0 \(numeric\) zero for main chain  
    "status": "active" \(string\) "active" for the main chain  
  },  
  {  
    "height": xxxx,  
    "hash": "xxxx",  
    "branchlen": 1 \(numeric\) length of branch connecting the tip to the main chain  
    "status": "xxxx" \(string\) status of the chain \(active, valid-fork, valid-headers, headers-only, invalid\)  
  }  
\]  
  
**Possible values for status:**  
1. "invalid" This branch contains at least one invalid block  
2. "headers-only" Not all blocks for this branch are available, but the headers are valid  
3. "valid-headers" All blocks are available for this branch, but they were never fully validated  
4. "valid-fork" This branch is not part of the active chain, but is fully validated  
5. "active" This is the tip of the active main chain, which is certainly valid  
  
**Examples:**  
&gt; nix-cli getchaintips  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getchaintips", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getchaintxstats (nblocks blockhash)` Compute statistics about the total number and rate of transactions in the chain.  
  
**Arguments:**  
1. nblocks \(numeric, optional\) Size of the window in number of blocks \(default: one month\).  
2. "blockhash" \(string, optional\) The hash of the block that ends the window.  
  
**Result:**  
{  
  "time": xxxxx, \(numeric\) The timestamp for the final block in the window in UNIX format.  
  "txcount": xxxxx, \(numeric\) The total number of transactions in the chain up to that point.  
  "window\_block\_count": xxxxx, \(numeric\) Size of the window in number of blocks.  
  "window\_tx\_count": xxxxx, \(numeric\) The number of transactions in the window. Only returned if "window\_block\_count" is &gt; 0.  
  "window\_interval": xxxxx, \(numeric\) The elapsed time in the window in seconds. Only returned if "window\_block\_count" is &gt; 0.  
  "txrate": x.xx, \(numeric\) The average rate of transactions per second in the window. Only returned if "window\_interval" is &gt; 0.  
}  
  
**Examples:**  
&gt; nix-cli getchaintxstats  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getchaintxstats", "params": \[2016\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getdifficulty` Returns the proof-of-stake difficulty as a multiple of the minimum difficulty.  
  
**Result:**  
n.nnn \(numeric\) the proof-of-work difficulty as a multiple of the minimum difficulty.  
  
**Examples:**  
&gt; nix-cli getdifficulty  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getdifficulty", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getmempoolancestors <txid> (verbose)` If txid is in the mempool, returns all in-mempool ancestors.  
  
**Arguments:**  
1. "txid" \(string, required\) The transaction id \(must be in mempool\)  
2. verbose \(boolean, optional, default=false\) True for a json object, false for array of transaction ids  
  
**Result \(for verbose=false\):**  
\[ \(json array of strings\)  
  "transactionid" \(string\) The transaction id of an in-mempool ancestor transaction  
  ,...  
\]  
  
**Result \(for verbose=true\):**  
{ \(json object\)  
  "transactionid" : { \(json object\)  
  "size" : n, \(numeric\) virtual transaction size as defined in BIP 141. This is different from actual serialized size for witness transactions as witness data is discounted.  
  "fee" : n, \(numeric\) transaction fee in NIX  
  "modifiedfee" : n, \(numeric\) transaction fee with fee deltas used for mining priority  
  "time" : n, \(numeric\) local time transaction entered pool in seconds since 1 Jan 1970 GMT  
  "height" : n, \(numeric\) block height when transaction entered pool  
  "descendantcount" : n, \(numeric\) number of in-mempool descendant transactions \(including this one\)  
  "descendantsize" : n, \(numeric\) virtual transaction size of in-mempool descendants \(including this one\)  
  "descendantfees" : n, \(numeric\) modified fees \(see above\) of in-mempool descendants \(including this one\)  
  "ancestorcount" : n, \(numeric\) number of in-mempool ancestor transactions \(including this one\)  
  "ancestorsize" : n, \(numeric\) virtual transaction size of in-mempool ancestors \(including this one\)  
  "ancestorfees" : n, \(numeric\) modified fees \(see above\) of in-mempool ancestors \(including this one\)  
  "wtxid" : hash, \(string\) hash of serialized transaction, including witness data  
  "depends" : \[ \(array\) unconfirmed transactions used as inputs for this transaction  
  "transactionid", \(string\) parent transaction id  
  ... \]  
  }, ...  
}  
  
**Examples:**  
&gt; nix-cli getmempoolancestors "mytxid"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmempoolancestors", "params": \["mytxid"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getmempooldescendants <txid> (verbose)` If txid is in the mempool, returns all in-mempool descendants.  
  
**Arguments:**  
1. "txid" \(string, required\) The transaction id \(must be in mempool\)  
2. verbose \(boolean, optional, default=false\) True for a json object, false for array of transaction ids  
  
**Result \(for verbose=false\):**  
\[ \(json array of strings\)  
  "transactionid" \(string\) The transaction id of an in-mempool descendant transaction  
  ,...  
\]  
  
**Result \(for verbose=true\):**  
{ \(json object\)  
  "transactionid" : { \(json object\)  
  "size" : n, \(numeric\) virtual transaction size as defined in BIP 141. This is different from actual serialized size for witness transactions as witness data is discounted.  
  "fee" : n, \(numeric\) transaction fee in NIX  
  "modifiedfee" : n, \(numeric\) transaction fee with fee deltas used for mining priority  
  "time" : n, \(numeric\) local time transaction entered pool in seconds since 1 Jan 1970 GMT  
  "height" : n, \(numeric\) block height when transaction entered pool  
  "descendantcount" : n, \(numeric\) number of in-mempool descendant transactions \(including this one\)  
  "descendantsize" : n, \(numeric\) virtual transaction size of in-mempool descendants \(including this one\)  
  "descendantfees" : n, \(numeric\) modified fees \(see above\) of in-mempool descendants \(including this one\)  
  "ancestorcount" : n, \(numeric\) number of in-mempool ancestor transactions \(including this one\)  
  "ancestorsize" : n, \(numeric\) virtual transaction size of in-mempool ancestors \(including this one\)  
  "ancestorfees" : n, \(numeric\) modified fees \(see above\) of in-mempool ancestors \(including this one\)  
  "wtxid" : hash, \(string\) hash of serialized transaction, including witness data  
  "depends" : \[ \(array\) unconfirmed transactions used as inputs for this transaction  
  "transactionid", \(string\) parent transaction id  
  ... \]  
  }, ...  
}  
  
**Examples:**  
&gt; nix-cli getmempooldescendants "mytxid"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmempooldescendants", "params": \["mytxid"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getmempoolentry <txid>` Returns mempool data for given transaction  
  
**Arguments:**  
1. "txid" \(string, required\) The transaction id \(must be in mempool\)  
  
**Result:**  
{ \(json object\)  
  "size" : n, \(numeric\) virtual transaction size as defined in BIP 141. This is different from actual serialized size for witness transactions as witness data is discounted.  
  "fee" : n, \(numeric\) transaction fee in NIX  
  "modifiedfee" : n, \(numeric\) transaction fee with fee deltas used for mining priority  
  "time" : n, \(numeric\) local time transaction entered pool in seconds since 1 Jan 1970 GMT  
  "height" : n, \(numeric\) block height when transaction entered pool  
  "descendantcount" : n, \(numeric\) number of in-mempool descendant transactions \(including this one\)  
  "descendantsize" : n, \(numeric\) virtual transaction size of in-mempool descendants \(including this one\)  
  "descendantfees" : n, \(numeric\) modified fees \(see above\) of in-mempool descendants \(including this one\)  
  "ancestorcount" : n, \(numeric\) number of in-mempool ancestor transactions \(including this one\)  
  "ancestorsize" : n, \(numeric\) virtual transaction size of in-mempool ancestors \(including this one\)  
  "ancestorfees" : n, \(numeric\) modified fees \(see above\) of in-mempool ancestors \(including this one\)  
  "wtxid" : hash, \(string\) hash of serialized transaction, including witness data  
  "depends" : \[ \(array\) unconfirmed transactions used as inputs for this transaction  
  "transactionid", \(string\) parent transaction id  
  ... \]  
}  
  
**Examples:**  
&gt; nix-cli getmempoolentry "mytxid"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmempoolentry", "params": \["mytxid"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getmempoolinfo` Returns details on the active state of the TX memory pool.  
  
**Result:**  
{  
  "size": xxxxx, \(numeric\) Current tx count  
  "bytes": xxxxx, \(numeric\) Sum of all virtual transaction sizes as defined in BIP 141. Differs from actual serialized size because witness data is discounted  
  "usage": xxxxx, \(numeric\) Total memory usage for the mempool  
  "maxmempool": xxxxx, \(numeric\) Maximum memory usage for the mempool  
  "mempoolminfee": xxxxx \(numeric\) Minimum fee rate in NIX/kB for tx to be accepted. Is the maximum of minrelaytxfee and minimum mempool fee  
  "minrelaytxfee": xxxxx \(numeric\) Current minimum relay fee for transactions  
}  
  
**Examples:**  
&gt; nix-cli getmempoolinfo  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmempoolinfo", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getrawmempool (verbose)` Returns all transaction ids in memory pool as a json array of string transaction ids. Hint: use getmempoolentry to fetch a specific transaction from the mempool.  
  
**Arguments:**  
1. verbose \(boolean, optional, default=false\) True for a json object, false for array of transaction ids  
  
**Result: \(for verbose = false\):**  
\[ \(json array of string\)  
  "transactionid" \(string\) The transaction id  
  ,...  
\]  
  
**Result: \(for verbose = true\):**  
{ \(json object\)  
  "transactionid" : { \(json object\)  
  "size" : n, \(numeric\) virtual transaction size as defined in BIP 141. This is different from actual serialized size for witness transactions as witness data is discounted.  
  "fee" : n, \(numeric\) transaction fee in NIX  
  "modifiedfee" : n, \(numeric\) transaction fee with fee deltas used for mining priority  
  "time" : n, \(numeric\) local time transaction entered pool in seconds since 1 Jan 1970 GMT  
  "height" : n, \(numeric\) block height when transaction entered pool  
  "descendantcount" : n, \(numeric\) number of in-mempool descendant transactions \(including this one\)  
  "descendantsize" : n, \(numeric\) virtual transaction size of in-mempool descendants \(including this one\)  
  "descendantfees" : n, \(numeric\) modified fees \(see above\) of in-mempool descendants \(including this one\)  
  "ancestorcount" : n, \(numeric\) number of in-mempool ancestor transactions \(including this one\)  
  "ancestorsize" : n, \(numeric\) virtual transaction size of in-mempool ancestors \(including this one\)  
  "ancestorfees" : n, \(numeric\) modified fees \(see above\) of in-mempool ancestors \(including this one\)  
  "wtxid" : hash, \(string\) hash of serialized transaction, including witness data  
  "depends" : \[ \(array\) unconfirmed transactions used as inputs for this transaction  
  "transactionid", \(string\) parent transaction id  
  ... \]  
  }, ...  
}  
  
**Examples:**  
&gt; nix-cli getrawmempool true  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getrawmempool", "params": \[true\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`gettxout "txid" n (include_mempool)` Returns details about an unspent transaction output.  
  
**Arguments:**  
1. "txid" \(string, required\) The transaction id  
2. "n" \(numeric, required\) vout number  
3. "include\_mempool" \(boolean, optional\) Whether to include the mempool. Default: true. Note that an unspent output that is spent in the mempool won't appear.  
  
**Result:**  
{  
  "bestblock" : "hash", \(string\) the block hash  
  "confirmations" : n, \(numeric\) The number of confirmations  
  "value" : x.xxx, \(numeric\) The transaction value in NIX  
  "scriptPubKey" : { \(json object\)  
  "asm" : "code", \(string\)  
  "hex" : "hex", \(string\)  
  "reqSigs" : n, \(numeric\) Number of required signatures  
  "type" : "pubkeyhash", \(string\) The type, eg pubkeyhash  
  "addresses" : \[ \(array of string\) array of nix addresses  
  "address" \(string\) nix address  
  ,...  
  \]  
  },  
  "coinbase" : true\|false \(boolean\) Coinbase or not  
}  
  
**Examples:**  
Get unspent transactions  
&gt; nix-cli listunspent  
View the details  
&gt; nix-cli gettxout "txid" 1  
As a json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "gettxout", "params": \["txid", 1\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`gettxoutproof ["txid",...] (blockhash)` Returns a hex-encoded proof that "txid" was included in a block. NOTE: By default this function only works sometimes. This is when there is an unspent output in the utxo for this transaction. To make it always work, you need to maintain a transaction index, using the -txindex command line option or specify the block in which the transaction is included manually \(by blockhash\).  
  
**Arguments:**  
1. "txids" \(string\) A json array of txids to filter  
\[  
  "txid" \(string\) A transaction hash  
  ,...  
\]  
2. "blockhash" \(string, optional\) If specified, looks for txid in the block with this hash  
  
**Result:**  
"data" \(string\) A string that is a serialized, hex-encoded data for the proof.

`gettxoutsetinfo` Returns statistics about the unspent transaction output set. NOTE: this call may take some time.  
  
**Result:**  
{  
  "height":n, \(numeric\) The current block height \(index\)  
  "bestblock": "hex", \(string\) the best block hash hex  
  "transactions": n, \(numeric\) The number of transactions  
  "txouts": n, \(numeric\) The number of output transactions  
  "bogosize": n, \(numeric\) A meaningless metric for UTXO set size  
  "hash\_serialized\_2": "hash", \(string\) The serialized hash  
  "disk\_size": n, \(numeric\) The estimated size of the chainstate on disk  
  "total\_amount": x.xxx \(numeric\) The total amount  
}  
  
**Examples:**  
&gt; nix-cli gettxoutsetinfo  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "gettxoutsetinfo", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`preciousblock "blockhash"`  Treats a block as if it were received before others with the same work. A later preciousblock call can override the effect of an earlier one. The effects of preciousblock are not retained across restarts.  
  
**Arguments:**  
1. "blockhash" \(string, required\) the hash of the block to mark as precious  
  
**Examples:**  
&gt; nix-cli preciousblock "blockhash"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "preciousblock", "params": \["blockhash"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`pruneblockchain`   
  
**Arguments:**  
1. "height" \(numeric, required\) The block height to prune up to. May be set to a discrete height, or a unix timestamp to prune blocks whose block time is at least 2 hours older than the provided timestamp.  
  
**Result:**  
n \(numeric\) Height of the last block pruned.  
  
**Examples:**  
&gt; nix-cli pruneblockchain 1000  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "pruneblockchain", "params": \[1000\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`savemempool` Dumps the mempool to disk.  
  
**Examples:**  
&gt; nix-cli savemempool  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "savemempool", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`verifychain (checklevel nblocks)` Verifies blockchain database.  
  
**Arguments:**  
1. checklevel \(numeric, optional, 0-4, default=3\) How thorough the block verification is.  
2. nblocks \(numeric, optional, default=6, 0=all\) The number of blocks to check.  
  
**Result:**  
true\|false \(boolean\) Verified or not  
  
**Examples:**  
&gt; nix-cli verifychain  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "verifychain", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`verifytxoutproof "proof"` Verifies that a proof points to a transaction in a block, returning the transaction it commits to and throwing an RPC error if the block is not in our best chain.  
  
**Arguments:**  
1. "proof" \(string, required\) The hex-encoded proof generated by gettxoutproof  
  
**Result:**  
\["txid"\] \(array, strings\) The txid\(s\) which the proof commits to, or empty array if the proof is invalid

## Control

`getmemoryinfo ("mode")` Returns an object containing information about memory usage.  
  
**Arguments:**  
1. "mode" determines what kind of information is returned. This argument is optional, the default mode is "stats".  
- "stats" returns general statistics about memory usage in the daemon.  
- "mallocinfo" returns an XML string describing low-level heap state \(only available if compiled with glibc 2.10+\).  
  
**Result \(mode "stats"\):**  
{  
  "locked": { \(json object\) Information about locked memory manager  
  "used": xxxxx, \(numeric\) Number of bytes used  
  "free": xxxxx, \(numeric\) Number of bytes available in current arenas  
  "total": xxxxxxx, \(numeric\) Total number of bytes managed  
  "locked": xxxxxx, \(numeric\) Amount of bytes that succeeded locking. If this number is smaller than total, locking pages failed at some point and key data could be swapped to disk.  
  "chunks\_used": xxxxx, \(numeric\) Number allocated chunks  
  "chunks\_free": xxxxx, \(numeric\) Number unused chunks  
  }  
}  
  
**Result \(mode "mallocinfo"\):**  
"&lt;malloc version="1"&gt;..."  
  
**Examples:**  
&gt; nix-cli getmemoryinfo  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmemoryinfo", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`help ("command")` List all commands, or get help for a specified command.  
  
**Arguments:**  
1. "command" \(string, optional\) The command to get help on  
  
**Result:**  
"text" \(string\) The help text

`logging (<include> <exclude>)` Gets and sets the logging configuration. When called without an argument, returns the list of categories with status that are currently being debug logged or not. When called with arguments, adds or removes categories from debug logging and return the lists above. The arguments are evaluated in order "include", "exclude". If an item is both included and excluded, it will thus end up being excluded. The valid logging categories are: net, tor, mempool, http, bench, zmq, db, rpc, estimatefee, addrman, selectcoins, reindex, cmpctblock, rand, prune, proxy, mempoolrej, libevent, coindb, qt, leveldb  
  
In addition, the following are available as category names with special meanings:  
 - "all", "1" : represent all logging categories.  
 - "none", "0" : even if other logging categories are specified, ignore all of them.  
  
**Arguments:**  
1. "include" \(array of strings, optional\) A json array of categories to add debug logging  
\[  
  "category" \(string\) the valid logging category  
  ,...  
\]  
2. "exclude" \(array of strings, optional\) A json array of categories to remove debug logging  
\[  
  "category" \(string\) the valid logging category  
  ,...  
\]  
  
**Result:**  
{ \(json object where keys are the logging categories, and values indicates its status  
  "category": 0\|1, \(numeric\) if being debug logged or not. 0:inactive, 1:active  
  ...  
}  
  
**Examples:**  
&gt; nix-cli logging "\[\"all\"\]" "\[\"http\"\]"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "logging", "params": \[\["all"\], "\[libevent\]"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`stop` Stop NIX server.

`uptime` Returns the total uptime of the server.  
  
**Result:**  
ttt \(numeric\) The number of seconds that the server has been running  
  
**Examples:**  
&gt; nix-cli uptime  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "uptime", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/uptime

## Generating

`generate <nblocks> (maxtries)` Mine up to nblocks blocks immediately \(before the RPC call returns\) to an address in the wallet.  
  
**Arguments:**  
1. nblocks \(numeric, required\) How many blocks are generated immediately.  
2. maxtries \(numeric, optional\) How many iterations to try \(default = 1000000\).  
  
**Result:**  
\[ blockhashes \] \(array\) hashes of blocks generated  
  
**Examples:**  
Generate 11 blocks  
&gt; nix-cli generate 11

`generatetoaddress <nblocks> <address> (maxtries)` Mine blocks immediately to a specified address \(before the RPC call returns\)  
  
**Arguments:**  
1. nblocks \(numeric, required\) How many blocks are generated immediately.  
2. address \(string, required\) The address to send the newly generated nix to.  
3. maxtries \(numeric, optional\) How many iterations to try \(default = 1000000\).  
  
**Result:**  
\[ blockhashes \] \(array\) hashes of blocks generated  
  
**Examples:**  
Generate 11 blocks to myaddress  
&gt; nix-cli generatetoaddress 11 "myaddress"

## Mining

`getblocktemplate (TemplateRequest)` If the request parameters include a 'mode' key, that is used to explicitly select between the default 'template' request or a 'proposal'. It returns data needed to construct a block to work on.  
  
For full specification, see BIPs 22, 23, 9, and 145:  
 https://github.com/bitcoin/bips/blob/master/bip-0022.mediawiki  
 https://github.com/bitcoin/bips/blob/master/bip-0023.mediawiki  
 https://github.com/bitcoin/bips/blob/master/bip-0009.mediawiki\#getblocktemplate\_changes  
 https://github.com/bitcoin/bips/blob/master/bip-0145.mediawiki  
  
**Arguments:**  
1. template\_request \(json object, optional\) A json object in the following spec  
{  
  "mode":"template" \(string, optional\) This must be set to "template", "proposal" \(see BIP 23\), or omitted  
  "capabilities":\[ \(array, optional\) A list of strings  
  "support" \(string\) client side supported feature, 'longpoll', 'coinbasetxn', 'coinbasevalue', 'proposal', 'serverlist', 'workid'  
  ,...  
  \],  
    "rules":\[ \(array, optional\) A list of strings  
    "support" \(string\) client side supported softfork deployment  
    ,...  
  \]  
}  
  
**Result:**  
{  
  "version" : n, \(numeric\) The preferred block version  
  "rules" : \[ "rulename", ... \], \(array of strings\) specific block rules that are to be enforced  
  "vbavailable" : { \(json object\) set of pending, supported versionbit \(BIP 9\) softfork deployments  
  "rulename" : bitnumber \(numeric\) identifies the bit number as indicating acceptance and readiness for the named softfork rule  
  ,...  
},  
  "vbrequired" : n, \(numeric\) bit mask of versionbits the server requires set in submissions  
  "previousblockhash" : "xxxx", \(string\) The hash of current highest block  
  "transactions" : \[ \(array\) contents of non-coinbase transactions that should be included in the next block  
  {  
    "data" : "xxxx", \(string\) transaction data encoded in hexadecimal \(byte-for-byte\)  
    "txid" : "xxxx", \(string\) transaction id encoded in little-endian hexadecimal  
    "hash" : "xxxx", \(string\) hash encoded in little-endian hexadecimal \(including witness data\)  
    "depends" : \[ \(array\) array of numbers  
    n \(numeric\) transactions before this one \(by 1-based index in 'transactions' list\) that must be present in the final block if this one is  
    ,...  
  \],  
  "fee": n, \(numeric\) difference in value between transaction inputs and outputs \(in satoshis\); for coinbase transactions, this is a negative Number of the total collected block fees \(ie, not including the block subsidy\); if key is not present, fee is unknown and clients MUST NOT assume there isn't one  
  "sigops" : n, \(numeric\) total SigOps cost, as counted for purposes of block limits; if key is not present, sigop cost is unknown and clients MUST NOT assume it is zero  
  "weight" : n, \(numeric\) total transaction weight, as counted for purposes of block limits  
  "required" : true\|false \(boolean\) if provided and true, this transaction must be in the final block  
  }  
  ,...  
  \],  
  "coinbaseaux" : { \(json object\) data that should be included in the coinbase's scriptSig content  
  "flags" : "xx" \(string\) key name is to be ignored, and value included in scriptSig  
  },  
  "coinbasevalue" : n, \(numeric\) maximum allowable input to coinbase transaction, including the generation award and transaction fees \(in satoshis\)  
  "coinbasetxn" : { ... }, \(json object\) information for coinbase transaction  
  "target" : "xxxx", \(string\) The hash target  
  "mintime" : xxx, \(numeric\) The minimum timestamp appropriate for next block time in seconds since epoch \(Jan 1 1970 GMT\)  
  "mutable" : \[ \(array of string\) list of ways the block template may be changed  
  "value" \(string\) A way the block template may be changed, e.g. 'time', 'transactions', 'prevblock'  
  ,...  
  \],  
  "noncerange" : "00000000ffffffff",\(string\) A range of valid nonces  
  "sigoplimit" : n, \(numeric\) limit of sigops in blocks  
  "sizelimit" : n, \(numeric\) limit of block size  
  "weightlimit" : n, \(numeric\) limit of block weight  
  "curtime" : ttt, \(numeric\) current timestamp in seconds since epoch \(Jan 1 1970 GMT\)  
  "bits" : "xxxxxxxx", \(string\) compressed target of next block  
  "height" : n \(numeric\) The height of the next block  
  "ghostnode" : { \(json object\) required ghostnode payee that must be included in the next block  
  "payee" : "xxxx", \(string\) payee address  
  "script" : "xxxx", \(string\) payee scriptPubKey  
  "amount": n \(numeric\) required amount to pay  
  },  
  "ghostnode\_payments\_started" : true\|false, \(boolean\) true, if ghostnode payments started  
}  
  
**Examples:**  
&gt; nix-cli getblocktemplate  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblocktemplate", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getmininginfo` Returns a json object containing mining-related information.  
  
**Result:**  
{  
  "blocks": nnn, \(numeric\) The current block  
  "currentblockweight": nnn, \(numeric\) The last block weight  
  "currentblocktx": nnn, \(numeric\) The last block transaction  
  "difficulty": xxx.xxxxx \(numeric\) The current difficulty  
  "networkhashps": nnn, \(numeric\) The network hashes per second  
  "pooledtx": n \(numeric\) The size of the mempool  
  "chain": "xxxx", \(string\) current network name as defined in BIP70 \(main, test, regtest\)  
  "warnings": "..." \(string\) any network and blockchain warnings  
  "errors": "..." \(string\) DEPRECATED. Same as warnings. Only shown when nixd is started with -deprecatedrpc=getmininginfo  
}  
  
**Examples:**  
&gt; nix-cli getmininginfo  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmininginfo", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getnetworkhashps (nblocks height)` Returns the estimated network hashes per second based on the last n blocks. Pass in \[blocks\] to override \# of blocks, -1 specifies since last difficulty change. Pass in \[height\] to estimate the network speed at the time when a certain block was found.  
  
**Arguments:**  
1. nblocks \(numeric, optional, default=120\) The number of blocks, or -1 for blocks since last difficulty change.  
2. height \(numeric, optional, default=-1\) To estimate at the time of the given height.  
  
**Result:**  
x \(numeric\) Hashes per second estimated  
  
**Examples:**  
&gt; nix-cli getnetworkhashps  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getnetworkhashps", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`prioitisetransaction <txid> <dummy value> <fee delta>` Accepts the transaction into mined blocks at a higher \(or lower\) priority  
  
**Arguments:**  
1. "txid" \(string, required\) The transaction id.  
2. dummy \(numeric, optional\) API-Compatibility for previous API. Must be zero or null. DEPRECATED. For forward compatibility use named arguments and omit this parameter.  
3. fee\_delta \(numeric, required\) The fee value \(in satoshis\) to add \(or subtract, if negative\). The fee is not actually paid, only the algorithm for selecting transactions into a block considers the transaction as it would have paid a higher \(or lower\) fee.  
  
**Result:**  
true \(boolean\) Returns true  
  
**Examples:**  
&gt; nix-cli prioritisetransaction "txid" 0.0 10000  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "prioritisetransaction", "params": \["txid", 0.0, 10000\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`submitblock "hexdata" ("dummy")` Attempts to submit new block to network. See https://en.bitcoin.it/wiki/BIP\_0022 for full specification.  
  
**Arguments:**  
1. "hexdata" \(string, required\) the hex-encoded block data to submit  
2. "dummy" \(optional\) dummy value, for compatibility with BIP22. This value is ignored.  
  
**Examples:**  
&gt; nix-cli submitblock "mydata"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "submitblock", "params": \["mydata"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

## Mnemonic

`mnemonic new|decode|addchecksum|dumpwords|listlanguages`  
  `mnemonic new ( "password" language nBytesEntropy bip44 )` Generate a new extended key and mnemonic password, can be blank , default blank language, english\|french\|japanese\|spanish\|chinese\_s\|chinese\_t\|italian\|korean, default english nBytesEntropy, 16 -&gt; 64, default 32 bip44, true\|false, default true  
  `mnemonic decode "password" "mnemonic" ( bip44 )` Decode mnemonic bip44, true\|false, default true mnemonic addchecksum "mnemonic" Add checksum words to mnemonic. Final no of words in mnemonic must be divisible by three.  
  `mnemonic dumpwords ( "language" )` Print list of words. language, default english  
  `mnemonic listlanguages` Print list of supported languages.

## Network

`addnode "node" "add|remove|onetry"` Attempts to add or remove a node from the addnode list. Or try a connection to a node once. Nodes added using addnode \(or -connect\) are protected from DoS disconnection and are not required to be full nodes/support SegWit as other outbound peers are \(though such peers will not be synced from\).  
  
**Arguments:**  
1. "node" \(string, required\) The node \(see getpeerinfo for nodes\)  
2. "command" \(string, required\) 'add' to add a node to the list, 'remove' to remove a node from the list, 'onetry' to try a connection to the node once  
  
**Examples:**  
&gt; nix-cli addnode "192.168.0.6:8333" "onetry"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "addnode", "params": \["192.168.0.6:8333", "onetry"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`clearbanned` Clear all banned IPs.  
  
**Examples:**  
&gt; nix-cli clearbanned  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "clearbanned", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`disconnectnode "[address]" [nodeid]` Immediately disconnects from the specified peer node. Strictly one out of 'address' and 'nodeid' can be provided to identify the node. To disconnect by nodeid, either set 'address' to the empty string, or call using the named 'nodeid' argument only.  
  
**Arguments:**  
1. "address" \(string, optional\) The IP address/port of the node  
2. "nodeid" \(number, optional\) The node ID \(see getpeerinfo for node IDs\)  
  
**Examples:**  
&gt; nix-cli disconnectnode "192.168.0.6:8333"  
&gt; nix-cli disconnectnode "" 1  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "disconnectnode", "params": \["192.168.0.6:8333"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "disconnectnode", "params": \["", 1\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getaddednodeinfo ("node")` Returns information about the given added node, or all added nodes \(note that onetry addnodes are not listed here\)  
  
**Arguments:**  
1. "node" \(string, optional\) If provided, return information about this specific node, otherwise all nodes are returned.  
  
**Result:**  
\[  
  {  
    "addednode" : "192.168.0.201", \(string\) The node IP address or name \(as provided to addnode\)  
    "connected" : true\|false, \(boolean\) If connected  
    "addresses" : \[ \(list of objects\) Only when connected = true  
    {  
      "address" : "192.168.0.201:8333", \(string\) The nix server IP and port we're connected to  
      "connected" : "outbound" \(string\) connection, inbound or outbound  
    }  
  \]  
  }  
  ,...  
\]  
  
**Examples:**  
&gt; nix-cli getaddednodeinfo "192.168.0.201"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getaddednodeinfo", "params": \["192.168.0.201"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getconnectioncount` Returns the number of connections to other nodes.  
  
**Result:**  
n \(numeric\) The connection count  
  
**Examples:**  
&gt; nix-cli getconnectioncount  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getconnectioncount", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getnettotals` Returns information about network traffic, including bytes in, bytes out, and current time.  
  
**Result:**  
{  
  "totalbytesrecv": n, \(numeric\) Total bytes received  
  "totalbytessent": n, \(numeric\) Total bytes sent  
  "timemillis": t, \(numeric\) Current UNIX time in milliseconds  
  "uploadtarget":  
  {  
    "timeframe": n, \(numeric\) Length of the measuring timeframe in seconds  
    "target": n, \(numeric\) Target in bytes  
    "target\_reached": true\|false, \(boolean\) True if target is reached  
    "serve\_historical\_blocks": true\|false, \(boolean\) True if serving historical blocks  
    "bytes\_left\_in\_cycle": t, \(numeric\) Bytes left in current time cycle  
    "time\_left\_in\_cycle": t \(numeric\) Seconds left in current time cycle  
  }  
}  
  
**Examples:**  
&gt; nix-cli getnettotals  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getnettotals", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getnetworkinfo` Returns an object containing various state info regarding P2P networking.  
  
**Result:**  
{  
  "version": xxxxx, \(numeric\) the server version  
  "subversion": "/Satoshi:x.x.x/", \(string\) the server subversion string  
  "protocolversion": xxxxx, \(numeric\) the protocol version  
  "localservices": "xxxxxxxxxxxxxxxx", \(string\) the services we offer to the network  
  "localrelay": true\|false, \(bool\) true if transaction relay is requested from peers  
  "timeoffset": xxxxx, \(numeric\) the time offset  
  "connections": xxxxx, \(numeric\) the number of connections  
  "networkactive": true\|false, \(bool\) whether p2p networking is enabled  
  "networks": \[ \(array\) information per network  
  {  
    "name": "xxx", \(string\) network \(ipv4, ipv6 or onion\)  
    "limited": true\|false, \(boolean\) is the network limited using -onlynet?  
    "reachable": true\|false, \(boolean\) is the network reachable?  
    "proxy": "host:port" \(string\) the proxy that is used for this network, or empty if none  
    "proxy\_randomize\_credentials": true\|false, \(string\) Whether randomized credentials are used  
  }  
  ,...  
  \],  
  "relayfee": x.xxxxxxxx, \(numeric\) minimum relay fee for transactions in NIX/kB  
  "incrementalfee": x.xxxxxxxx, \(numeric\) minimum fee increment for mempool limiting or BIP 125 replacement in NIX/kB  
  "localaddresses": \[ \(array\) list of local addresses  
  {  
    "address": "xxxx", \(string\) network address  
    "port": xxx, \(numeric\) network port  
    "score": xxx \(numeric\) relative score  
  }  
  ,...  
  \]  
  "warnings": "..." \(string\) any network and blockchain warnings  
}  
  
**Examples:**  
&gt; nix-cli getnetworkinfo  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getnetworkinfo", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getpeerinfo` Returns data about each connected network node as a json array of objects.  
  
**Result:**  
\[  
  {  
    "id": n, \(numeric\) Peer index  
    "addr":"host:port", \(string\) The IP address and port of the peer  
    "addrbind":"ip:port", \(string\) Bind address of the connection to the peer  
    "addrlocal":"ip:port", \(string\) Local address as reported by the peer  
    "services":"xxxxxxxxxxxxxxxx", \(string\) The services offered  
    "relaytxes":true\|false, \(boolean\) Whether peer has asked us to relay transactions to it  
    "lastsend": ttt, \(numeric\) The time in seconds since epoch \(Jan 1 1970 GMT\) of the last send  
    "lastrecv": ttt, \(numeric\) The time in seconds since epoch \(Jan 1 1970 GMT\) of the last receive  
    "bytessent": n, \(numeric\) The total bytes sent  
    "bytesrecv": n, \(numeric\) The total bytes received  
    "conntime": ttt, \(numeric\) The connection time in seconds since epoch \(Jan 1 1970 GMT\)  
    "timeoffset": ttt, \(numeric\) The time offset in seconds  
    "pingtime": n, \(numeric\) ping time \(if available\)  
    "minping": n, \(numeric\) minimum observed ping time \(if any at all\)  
    "pingwait": n, \(numeric\) ping wait \(if non-zero\)  
    "version": v, \(numeric\) The peer version, such as 70001  
    "subver": "/Satoshi:0.8.5/", \(string\) The string version  
    "inbound": true\|false, \(boolean\) Inbound \(true\) or Outbound \(false\)  
    "addnode": true\|false, \(boolean\) Whether connection was due to addnode/-connect or if it was an automatic/inbound connection  
    "startingheight": n, \(numeric\) The starting height \(block\) of the peer  
    "banscore": n, \(numeric\) The ban score  
    "synced\_headers": n, \(numeric\) The last header we have in common with this peer  
    "synced\_blocks": n, \(numeric\) The last block we have in common with this peer  
    "inflight": \[  
      n, \(numeric\) The heights of blocks we're currently asking from this peer  
      ...  
    \],  
    "whitelisted": true\|false, \(boolean\) Whether the peer is whitelisted  
    "bytessent\_per\_msg": {  
    "addr": n, \(numeric\) The total bytes sent aggregated by message type  
    ...  
    },  
    "bytesrecv\_per\_msg": {  
    "addr": n, \(numeric\) The total bytes received aggregated by message type  
    ...  
    }  
  }  
  ,...  
\]  
  
**Examples:**  
&gt; nix-cli getpeerinfo  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getpeerinfo", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`listbanned` List all banned IPs/Subnets.  
  
**Examples:**  
&gt; nix-cli listbanned  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listbanned", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`ping` Requests that a ping be sent to all other nodes, to measure ping time. Results provided in getpeerinfo, pingtime and pingwait fields are decimal seconds. Ping command is handled in queue with all other commands, so it measures processing backlog, not just network ping.  
  
**Examples:**  
&gt; nix-cli ping  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "ping", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`setban "subnet" "add|remove" (bantime) (absolute)` Attempts to add or remove an IP/Subnet from the banned list.  
  
**Arguments:**  
1. "subnet" \(string, required\) The IP/Subnet \(see getpeerinfo for nodes IP\) with an optional netmask \(default is /32 = single IP\)  
2. "command" \(string, required\) 'add' to add an IP/Subnet to the list, 'remove' to remove an IP/Subnet from the list  
3. "bantime" \(numeric, optional\) time in seconds how long \(or until when if \[absolute\] is set\) the IP is banned \(0 or empty means using the default time of 24h which can also be overwritten by the -bantime startup argument\)  
4. "absolute" \(boolean, optional\) If set, the bantime must be an absolute timestamp in seconds since epoch \(Jan 1 1970 GMT\)  
  
**Examples:**  
&gt; nix-cli setban "192.168.0.6" "add" 86400  
&gt; nix-cli setban "192.168.0.0/24" "add"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "setban", "params": \["192.168.0.6", "add", 86400\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`setnetworkactive true|false` Disable/enable all p2p network activity.  
  
**Arguments:**  
1. "state" \(boolean, required\) true to enable networking, false to disable

## Raw Transactions

`combinerawtransaction ["hexstring",...]` Combine multiple partially signed transactions into one transaction. The combined transaction may be another partially signed transaction or a fully signed transaction.  
  
**Arguments:**  
1. "txs" \(string\) A json array of hex strings of partially signed transactions  
\[  
  "hexstring" \(string\) A transaction hash  
  ,...  
\]  
  
**Result:**  
"hex" \(string\) The hex-encoded raw transaction with signature\(s\)  
  
**Examples:**  
&gt; nix-cli combinerawtransaction \["myhex1", "myhex2", "myhex3"\]

`createrawtransaction [{"txid":"id","vout":n},...] {"address":amount,"data":"hex",...} (locktime) (replaceable)` Create a transaction spending the given inputs and creating new outputs. Outputs can be addresses or data. Returns hex-encoded raw transaction. Note that the transaction's inputs are not signed, and it is not stored in the wallet or transmitted to the network.  
  
**Arguments:**  
1. "inputs" \(array, required\) A json array of json objects  
\[  
  {  
    "txid":"id", \(string, required\) The transaction id  
    "vout":n, \(numeric, required\) The output number  
    "sequence":n \(numeric, optional\) The sequence number  
  }  
  ,...  
\]  
2. "outputs" \(object, required\) a json object with outputs  
{  
  "address": x.xxx, \(numeric or string, required\) The key is the nix address, the numeric value \(can be string\) is the NIX amount  
  "data": "hex" \(string, required\) The key is "data", the value is hex encoded data  
  ,...  
}  
3. locktime \(numeric, optional, default=0\) Raw locktime. Non-0 value also locktime-activates inputs  
4. replaceable \(boolean, optional, default=false\) Marks this transaction as BIP125 replaceable. Allows this transaction to be replaced by a transaction with higher fees. If provided, it is an error if explicit sequence numbers are incompatible.  
  
**Result:**  
"transaction" \(string\) hex string of the transaction  
  
**Examples:**  
&gt; nix-cli createrawtransaction "\[{\"txid\":\"myid\",\"vout\":0}\]" "{\"address\":0.01}"  
&gt; nix-cli createrawtransaction "\[{\"txid\":\"myid\",\"vout\":0}\]" "{\"data\":\"00010203\"}"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "createrawtransaction", "params": \["\[{\"txid\":\"myid\",\"vout\":0}\]", "{\"address\":0.01}"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "createrawtransaction", "params": \["\[{\"txid\":\"myid\",\"vout\":0}\]", "{\"data\":\"00010203\"}"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`decoderawtransaction "hexstring" (iswitness)` Return a JSON object representing the serialized, hex-encoded transaction.  
  
**Arguments:**  
1. "hexstring" \(string, required\) The transaction hex string  
2. iswitness \(boolean, optional\) Whether the transaction hex is a serialized witness transaction. If iswitness is not present, heuristic tests will be used in decoding.  
  
**Result:**  
{  
  "txid" : "id", \(string\) The transaction id  
  "hash" : "id", \(string\) The transaction hash \(differs from txid for witness transactions\)  
  "size" : n, \(numeric\) The transaction size  
  "vsize" : n, \(numeric\) The virtual transaction size \(differs from size for witness transactions\)  
  "version" : n, \(numeric\) The version  
  "locktime" : ttt, \(numeric\) The lock time  
  "vin" : \[ \(array of json objects\)  
  {  
    "txid": "id", \(string\) The transaction id  
    "vout": n, \(numeric\) The output number  
    "scriptSig": { \(json object\) The script  
    "asm": "asm", \(string\) asm  
    "hex": "hex" \(string\) hex  
  },  
  "txinwitness": \["hex", ...\] \(array of string\) hex-encoded witness data \(if any\)  
  "sequence": n \(numeric\) The script sequence number  
}  
,...  
\],  
"vout" : \[ \(array of json objects\)  
{  
  "value" : x.xxx, \(numeric\) The value in NIX  
  "n" : n, \(numeric\) index  
  "scriptPubKey" : { \(json object\)  
  "asm" : "asm", \(string\) the asm  
  "hex" : "hex", \(string\) the hex  
  "reqSigs" : n, \(numeric\) The required sigs  
  "type" : "pubkeyhash", \(string\) The type, eg 'pubkeyhash'  
  "addresses" : \[ \(json array of string\)  
  "12tvKAXCxZjSmdNbao16dKXC8tRWfcF5oc" \(string\) nix address  
  ,...  
  \]  
  }  
}  
,...  
\],

}  
  
**Examples:**  
&gt; nix-cli decoderawtransaction "hexstring"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "decoderawtransaction", "params": \["hexstring"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`decodescript "hexstring"` Decode a hex-encoded script.  
  
**Arguments:**  
1. "hexstring" \(string\) the hex encoded script  
  
**Result:**  
{  
  "asm":"asm", \(string\) Script public key  
  "hex":"hex", \(string\) hex encoded public key  
  "type":"type", \(string\) The output type  
  "reqSigs": n, \(numeric\) The required signatures  
  "addresses": \[ \(json array of string\)  
  "address" \(string\) nix address  
  ,...  
  \],  
  "p2sh","address" \(string\) address of P2SH script wrapping this redeem script \(not returned if the script is already a P2SH\).  
}  
  
**Examples:**  
&gt; nix-cli decodescript "hexstring"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "decodescript", "params": \["hexstring"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`fundrawtransaction "hexstring" (options iswitness)` Add inputs to a transaction until it has enough in value to meet its out value. This will not modify existing inputs, and will add at most one change output to the outputs. No existing outputs will be modified unless "subtractFeeFromOutputs" is specified. Note that inputs which were signed may need to be resigned after completion since in/outputs have been added.  
The inputs added will not be signed, use signrawtransaction for that.  
Note that all existing inputs must have their previous output transaction be in the wallet.  
Note that all inputs selected must be of standard form and P2SH scripts must be in the wallet using importaddress or addmultisigaddress \(to calculate fees\).  
You can see whether this is the case by checking the "solvable" field in the listunspent output.  
Only pay-to-pubkey, multisig, and P2SH versions thereof are currently supported for watch-only  
  
**Arguments:**  
1. "hexstring" \(string, required\) The hex string of the raw transaction  
2. options \(object, optional\)  
{  
  "changeAddress" \(string, optional, default pool address\) The nix address to receive the change "changePosition" \(numeric, optional, default random\) The index of the change output  
  "change\_type" \(string, optional\) The output type to use. Only valid if changeAddress is not specified. Options are "legacy", "p2sh-segwit", and "bech32". Default is set by -changetype.  
  "includeWatching" \(boolean, optional, default false\) Also select inputs which are watch only  
  "lockUnspents" \(boolean, optional, default false\) Lock selected unspent outputs  
  "feeRate" \(numeric, optional, default not set: makes wallet determine the fee\) Set a specific fee rate in NIX/kB  
  "subtractFeeFromOutputs" \(array, optional\) A json array of integers. The fee will be equally deducted from the amount of each specified output. The outputs are specified by their zero-based index, before any change output is added. Those recipients will receive less nix than you enter in their corresponding amount field. If no outputs are specified here, the sender pays the fee.  
  \[vout\_index,...\]  
  "replaceable" \(boolean, optional\) Marks this transaction as BIP125 replaceable. Allows this transaction to be replaced by a transaction with higher fees  
  "conf\_target" \(numeric, optional\) Confirmation target \(in blocks\)  
  "estimate\_mode" \(string, optional, default=UNSET\) The fee estimate mode, must be one of:  
"UNSET"  
"ECONOMICAL"  
"CONSERVATIVE"  
}  
for backward compatibility: passing in a true instead of an object will result in {"includeWatching":true}  
3. iswitness \(boolean, optional\) Whether the transaction hex is a serialized witness transaction  
If iswitness is not present, heuristic tests will be used in decoding  
  
**Result:**  
{  
  "hex": "value", \(string\) The resulting raw transaction \(hex-encoded string\)  
  "fee": n, \(numeric\) Fee in NIX the resulting transaction pays  
  "changepos": n \(numeric\) The position of the added change output, or -1  
}  
  
**Examples:**  
Create a transaction with no inputs  
&gt; nix-cli createrawtransaction "\[\]" "{\"myaddress\":0.01}"  
Add sufficient unsigned inputs to meet the output value  
&gt; nix-cli fundrawtransaction "rawtransactionhex"  
Sign the transaction  
&gt; nix-cli signrawtransaction "fundedtransactionhex"  
Send the transaction  
&gt; nix-cli sendrawtransaction "signedtransactionhex"

`getrawtransaction "txid" (verbose "blockhash")`   
NOTE: By default this function only works for mempool transactions. If the -txindex option is enabled, it also works for blockchain transactions. If the block which contains the transaction is known, its hash can be provided even for nodes without -txindex. Note that if a blockhash is provided, only that block will be searched and if the transaction is in the mempool or other blocks, or if this node does not have the given block available, the transaction will not be found.  
DEPRECATED: for now, it also works for transactions with unspent outputs.  
  
Return the raw transaction data.  
  
If verbose is 'true', returns an Object with information about 'txid'.  
If verbose is 'false' or omitted, returns a string that is serialized, hex-encoded data for 'txid'.  
  
**Arguments:**  
1. "txid" \(string, required\) The transaction id  
2. verbose \(bool, optional, default=false\) If false, return a string, otherwise return a json object  
3. "blockhash" \(string, optional\) The block in which to look for the transaction  
  
**Result \(if verbose is not set or set to false\):**  
"data" \(string\) The serialized, hex-encoded data for 'txid'  
  
**Result \(if verbose is set to true\):**  
{  
  "in\_active\_chain": b, \(bool\) Whether specified block is in the active chain or not \(only present with explicit "blockhash" argument\)  
  "hex" : "data", \(string\) The serialized, hex-encoded data for 'txid'  
  "txid" : "id", \(string\) The transaction id \(same as provided\)  
  "hash" : "id", \(string\) The transaction hash \(differs from txid for witness transactions\)  
  "size" : n, \(numeric\) The serialized transaction size  
  "vsize" : n, \(numeric\) The virtual transaction size \(differs from size for witness transactions\)  
  "version" : n, \(numeric\) The version  
  "locktime" : ttt, \(numeric\) The lock time  
  "vin" : \[ \(array of json objects\)  
  {  
    "txid": "id", \(string\) The transaction id  
    "vout": n, \(numeric\)  
    "scriptSig": { \(json object\) The script  
    "asm": "asm", \(string\) asm  
    "hex": "hex" \(string\) hex  
  },  
  "sequence": n \(numeric\) The script sequence number  
  "txinwitness": \["hex", ...\] \(array of string\) hex-encoded witness data \(if any\)  
}  
,...  
\],  
"vout" : \[ \(array of json objects\)  
{  
  "value" : x.xxx, \(numeric\) The value in NIX  
  "n" : n, \(numeric\) index  
  "scriptPubKey" : { \(json object\)  
  "asm" : "asm", \(string\) the asm  
  "hex" : "hex", \(string\) the hex  
  "reqSigs" : n, \(numeric\) The required sigs  
  "type" : "pubkeyhash", \(string\) The type, eg 'pubkeyhash'  
  "addresses" : \[ \(json array of string\)  
  "address" \(string\) nix address  
  ,...  
  \]  
  }  
}  
,...  
\],  
"blockhash" : "hash", \(string\) the block hash  
"confirmations" : n, \(numeric\) The confirmations  
"time" : ttt, \(numeric\) The transaction time in seconds since epoch \(Jan 1 1970 GMT\)  
"blocktime" : ttt \(numeric\) The block time in seconds since epoch \(Jan 1 1970 GMT\)  
}  
  
**Examples:**  
&gt; nix-cli getrawtransaction "mytxid"  
&gt; nix-cli getrawtransaction "mytxid" true  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getrawtransaction", "params": \["mytxid", true\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  
&gt; nix-cli getrawtransaction "mytxid" false "myblockhash"  
&gt; nix-cli getrawtransaction "mytxid" true "myblockhash"

`sendrawtransaction "hexstring" (allowhighfees)` Submits raw transaction \(serialized, hex-encoded\) to local node and network. Also see createrawtransaction and signrawtransaction calls.  
  
**Arguments:**  
1. "hexstring" \(string, required\) The hex string of the raw transaction\)  
2. allowhighfees \(boolean, optional, default=false\) Allow high fees  
  
**Result:**  
"hex" \(string\) The transaction hash in hex  
  
**Examples:**  
Create a transaction  
&gt; nix-cli createrawtransaction "\[{\"txid\" : \"mytxid\",\"vout\":0}\]" "{\"myaddress\":0.01}"  
Sign the transaction, and get back the hex  
&gt; nix-cli signrawtransaction "myhex"  
Send the transaction \(signed hex\)  
&gt; nix-cli sendrawtransaction "signedhex"  
As a json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "sendrawtransaction", "params": \["signedhex"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`signrawtransaction "hexstring" ( [{"txid":"id","vout":n,"scriptPubKey":"hex","redeemScript":"hex"},...] ["privatekey1",...] sighashtype )`Sign inputs for raw transaction \(serialized, hex-encoded\).  
The second optional argument \(may be null\) is an array of previous transaction outputs that this transaction depends on but may not yet be in the block chain.  
The third optional argument \(may be null\) is an array of base58-encoded private keys that, if given, will be the only keys used to sign the transaction.  
Requires wallet passphrase to be set with walletpassphrase call.  
  
**Arguments:**  
1. "hexstring" \(string, required\) The transaction hex string  
2. "prevtxs" \(string, optional\) An json array of previous dependent transaction outputs  
\[ \(json array of json objects, or 'null' if none provided\)  
{  
  "txid":"id", \(string, required\) The transaction id  
  "vout":n, \(numeric, required\) The output number  
  "scriptPubKey": "hex", \(string, required\) script key  
  "redeemScript": "hex", \(string, required for P2SH or P2WSH\) redeem script  
  "amount": value \(numeric, required\) The amount spent  
}  
,...  
\]  
3. "privkeys" \(string, optional\) A json array of base58-encoded private keys for signing  
\[ \(json array of strings, or 'null' if none provided\)  
"privatekey" \(string\) private key in base58-encoding  
,...  
\]  
4. "sighashtype" \(string, optional, default=ALL\) The signature hash type. Must be one of  
"ALL"  
"NONE"  
"SINGLE"  
"ALL\|ANYONECANPAY"  
"NONE\|ANYONECANPAY"  
"SINGLE\|ANYONECANPAY"  
  
**Result:**  
{  
  "hex" : "value", \(string\) The hex-encoded raw transaction with signature\(s\)  
  "complete" : true\|false, \(boolean\) If the transaction has a complete set of signatures  
  "errors" : \[ \(json array of objects\) Script verification errors \(if there are any\)  
  {  
    "txid" : "hash", \(string\) The hash of the referenced, previous transaction  
    "vout" : n, \(numeric\) The index of the output to spent and used as input  
    "scriptSig" : "hex", \(string\) The hex-encoded signature script  
    "sequence" : n, \(numeric\) Script sequence number  
    "error" : "text" \(string\) Verification or signing error related to the input  
  }  
  ,...  
  \]  
}  
  
**Examples:**  
&gt; nix-cli signrawtransaction "myhex"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "signrawtransaction", "params": \["myhex"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

## Util

`createmultisig nrequired ["key",...]` Creates a multi-signature address with n signature of m keys required. It returns a json object with the address and redeemScript. DEPRECATION WARNING: Using addresses with createmultisig is deprecated. Clients must transition to using addmultisigaddress to create multisig addresses with addresses known to the wallet before upgrading to v0.17. To use the deprecated functionality, start nixd with -deprecatedrpc=createmultisig  
  
**Arguments:**  
1. nrequired \(numeric, required\) The number of required signatures out of the n keys or addresses.  
2. "keys" \(string, required\) A json array of hex-encoded public keys  
\[  
  "key" \(string\) The hex-encoded public key  
  ,...  
\]  
  
**Result:**  
{  
  "address":"multisigaddress", \(string\) The value of the new multisig address.  
  "redeemScript":"script" \(string\) The string value of the hex-encoded redemption script.  
}  
  
**Examples:**  
Create a multisig address from 2 public keys  
&gt; nix-cli createmultisig 2 "\[\"03789ed0bb717d88f7d321a368d905e7430207ebbd82bd342cf11ae157a7ace5fd\",\"03dbc6764b8884a92e871274b87583e6d5c2a58819473e17e107ef3f6aa5a61626\"\]"  
As a json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "createmultisig", "params": \[2, "\[\"03789ed0bb717d88f7d321a368d905e7430207ebbd82bd342cf11ae157a7ace5fd\",\"03dbc6764b8884a92e871274b87583e6d5c2a58819473e17e107ef3f6aa5a61626\"\]"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332

`estimatefee <nblocks>` DEPRECATED. Please use estimatesmartfee for more intelligent estimates. Estimates the approximate fee per kilobyte needed for a transaction to begin confirmation within nblocks blocks. Uses virtual transaction size of transaction as defined in BIP 141 \(witness data is discounted\).  
  
**Arguments:**  
1. nblocks \(numeric, required\)  
  
**Result:**  
n \(numeric\) estimated fee-per-kilobyte.  
A negative value is returned if not enough transactions and blocks have been observed to make an estimate.  
-1 is always returned for nblocks == 1 as it is impossible to calculate a fee that is high enough to get reliably included in the next block.  
  
**Example:**  
&gt; nix-cli estimatefee 6

`estimatesmartfee <conf_target> ("estimate_mode")` Estimates the approximate fee per kilobyte needed for a transaction to begin confirmation within conf\_target blocks if possible and return the number of blocks for which the estimate is valid. Uses virtual transaction size as defined in BIP 141 \(witness data is discounted\).  
  
**Arguments:**  
1. conf\_target \(numeric\) Confirmation target in blocks \(1 - 1008\)  
2. "estimate\_mode" \(string, optional, default=CONSERVATIVE\) The fee estimate mode. Whether to return a more conservative estimate which also satisfies a longer history. A conservative estimate potentially returns a higher feerate and is more likely to be sufficient for the desired target, but is not as responsive to short term drops in the prevailing fee market. Must be one of:  
"UNSET" \(defaults to CONSERVATIVE\)  
"ECONOMICAL"  
"CONSERVATIVE"  
  
**Result:**  
{  
  "feerate" : x.x, \(numeric, optional\) estimate fee rate in NIX/kB  
  "errors": \[ str... \] \(json array of strings, optional\) Errors encountered during processing  
  "blocks" : n \(numeric\) block number where estimate was found  
}  
The request target will be clamped between 2 and the highest target fee estimation is able to return based on how long it has been running. An error is returned if not enough transactions and blocks have been observed to make an estimate for any number of blocks.  
  
**Example:**  
&gt; nix-cli estimatesmartfee 6

`signmessagewithprivkey "privkey" "message"` Sign a message with the private key of an address  
  
**Arguments:**  
1. "privkey" \(string, required\) The private key to sign the message with.  
2. "message" \(string, required\) The message to create a signature of.  
  
**Result:**  
"signature" \(string\) The signature of the message encoded in base 64  
  
**Examples:**  
Create the signature  
&gt; nix-cli signmessagewithprivkey "privkey" "my message"  
Verify the signature  
&gt; nix-cli verifymessage "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "signature" "my message"  
As json rpc  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "signmessagewithprivkey", "params": \["privkey", "my message"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`validateaddress "address"` Return information about the given nix address.  
  
**Arguments:**  
1. "address" \(string, required\) The nix address to validate  
  
**Result:**  
{  
  "isvalid" : true\|false, \(boolean\) If the address is valid or not. If not, this is the only property returned.  
  "address" : "address", \(string\) The nix address validated  
  "scriptPubKey" : "hex", \(string\) The hex encoded scriptPubKey generated by the address  
  "ismine" : true\|false, \(boolean\) If the address is yours or not  
  "iswatchonly" : true\|false, \(boolean\) If the address is watchonly  
  "isscript" : true\|false, \(boolean, optional\) If the address is P2SH or P2WSH. Not included for unknown witness types.  
  "iswitness" : true\|false, \(boolean\) If the address is P2WPKH, P2WSH, or an unknown witness version  
  "witness\_version" : version \(number, optional\) For all witness output types, gives the version number.  
  "witness\_program" : "hex" \(string, optional\) For all witness output types, gives the script or key hash present in the address.  
  "script" : "type" \(string, optional\) The output script type. Only if "isscript" is true and the redeemscript is known. Possible types: nonstandard, pubkey, pubkeyhash, scripthash, multisig, nulldata, witness\_v0\_keyhash, witness\_v0\_scripthash, witness\_unknown  
  "hex" : "hex", \(string, optional\) The redeemscript for the P2SH or P2WSH address  
  "addresses" \(string, optional\) Array of addresses associated with the known redeemscript \(only if "iswitness" is false\). This field is superseded by the "pubkeys" field and the address inside "embedded".  
  \[  
    "address"  
    ,...  
  \]  
  "pubkeys" \(string, optional\) Array of pubkeys associated with the known redeemscript \(only if "script" is "multisig"\)  
  \[  
    "pubkey"  
    ,...  
  \]  
  "sigsrequired" : xxxxx \(numeric, optional\) Number of signatures required to spend multisig output \(only if "script" is "multisig"\)  
  "pubkey" : "publickeyhex", \(string, optional\) The hex value of the raw public key, for single-key addresses \(possibly embedded in P2SH or P2WSH\)  
  "embedded" : {...}, \(object, optional\) information about the address embedded in P2SH or P2WSH, if relevant and known. It includes all validateaddress output fields for the embedded address, excluding "isvalid", metadata \("timestamp", "hdkeypath", "hdmasterkeyid"\) and relation to the wallet \("ismine", "iswatchonly", "account"\).  
  "iscompressed" : true\|false, \(boolean\) If the address is compressed  
  "account" : "account" \(string\) DEPRECATED. The account associated with the address, "" is the default account  
  "timestamp" : timestamp, \(number, optional\) The creation time of the key if available in seconds since epoch \(Jan 1 1970 GMT\)  
  "hdkeypath" : "keypath" \(string, optional\) The HD keypath if the key is HD and available  
  "hdmasterkeyid" : "&lt;hash160&gt;" \(string, optional\) The Hash160 of the HD master pubkey  
}  
  
**Examples:**  
&gt; nix-cli validateaddress "1PSSGeFHDnKNxiEyFrD1wcEaHr9hrQDDWc"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "validateaddress", "params": \["1PSSGeFHDnKNxiEyFrD1wcEaHr9hrQDDWc"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`verifymessage "address" "signature" "message"` Verify a signed message  
  
**Arguments:**  
1. "address" \(string, required\) The nix address to use for the signature.  
2. "signature" \(string, required\) The signature provided by the signer in base 64 encoding \(see signmessage\).  
3. "message" \(string, required\) The message that was signed.  
  
**Result:**  
true\|false \(boolean\) If the signature is verified or not.  
  
**Examples:**  
Unlock the wallet for 30 seconds  
&gt; nix-cli walletpassphrase "mypassphrase" 30  
Create the signature  
&gt; nix-cli signmessage "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "my message"  
Verify the signature  
&gt; nix-cli verifymessage "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "signature" "my message"  
As json rpc  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "verifymessage", "params": \["1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX", "signature", "my message"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

## Wallet

`abandontransaction "txid"` Mark in-wallet transaction &lt;txid&gt; as abandoned. This will mark this transaction and all its in-wallet descendants as abandoned which will allow for their inputs to be respent. It can be used to replace "stuck" or evicted transactions. It only works on transactions which are not included in a block and are not currently in the mempool. It has no effect on transactions which are already conflicted or abandoned.  
  
**Arguments:**  
1. "txid" \(string, required\) The transaction id  
  
**Examples:**  
&gt; nix-cli abandontransaction "1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5fbf5d48d"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "abandontransaction", "params": \["1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5fbf5d48d"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`abortrescan` Stops current wallet rescan triggered by an RPC call, e.g. by an importprivkey call.  
  
**Examples:**  
Abort the running wallet rescan  
&gt; nix-cli abortrescan  
As a JSON-RPC call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "abortrescan", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`addmultisigaddress <nrequired> ["key",...] ( "account" "address_type" )` Add a nrequired-to-sign multisignature address to the wallet. Requires a new wallet backup. Each key is a NIX address or hex-encoded public key. This functionality is only intended for use with non-watchonly addresses. See \`importaddress\` for watchonly p2sh address support. If 'account' is specified \(DEPRECATED\), assign address to that account.  
  
**Arguments:**  
1. nrequired \(numeric, required\) The number of required signatures out of the n keys or addresses.  
2. "keys" \(string, required\) A json array of nix addresses or hex-encoded public keys  
\[  
  "address" \(string\) nix address or hex-encoded public key  
  ...,  
\]  
3. "account" \(string, optional\) DEPRECATED. An account to assign the addresses to.  
4. "address\_type" \(string, optional\) The address type to use. Options are "legacy", "p2sh-segwit", and "bech32". Default is set by -addresstype.  
  
**Result:**  
{  
  "address":"multisigaddress", \(string\) The value of the new multisig address.  
  "redeemScript":"script" \(string\) The string value of the hex-encoded redemption script.  
}  
Result \(DEPRECATED. To see this result in v0.16 instead, please start nixd with -deprecatedrpc=addmultisigaddress\). Clients should transition to the new output api before upgrading to v0.17.  
"address" \(string\) A nix address associated with the keys.  
  
**Examples:**  
Add a multisig address from 2 addresses  
&gt; nix-cli addmultisigaddress 2 "\[\"16sSauSf5pF2UkUwvKGq4qjNRzBZYqgEL5\",\"171sgjn4YtPu27adkKGrdDwzRTxnRkBfKV\"\]"  
As json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "addmultisigaddress", "params": \[2, "\[\"16sSauSf5pF2UkUwvKGq4qjNRzBZYqgEL5\",\"171sgjn4YtPu27adkKGrdDwzRTxnRkBfKV\"\]"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`backupwallet "destination"` Safely copies current wallet file to destination, which can be a directory or a path with filename.  
  
**Arguments:**  
1. "destination" \(string\) The destination directory or file  
  
**Examples:**  
&gt; nix-cli backupwallet "backup.dat"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "backupwallet", "params": \["backup.dat"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`bumpfee "txid" (options)` Bumps the fee of an opt-in-RBF transaction T, replacing it with a new transaction B. An opt-in RBF transaction with the given txid must be in the wallet. The command will pay the additional fee by decreasing \(or perhaps removing\) its change output. If the change output is not big enough to cover the increased fee, the command will currently fail instead of adding new inputs to compensate. \(A future implementation could improve this.\) The command will fail if the wallet or mempool contains a transaction that spends one of T's outputs.  
By default, the new fee will be calculated automatically using estimatefee. The user can specify a confirmation target for estimatefee.  
Alternatively, the user can specify totalFee, or use RPC settxfee to set a higher fee rate. At a minimum, the new fee rate must be high enough to pay an additional new relay fee \(incrementalfee returned by getnetworkinfo\) to enter the node's mempool.  
  
**Arguments:**  
1. txid \(string, required\) The txid to be bumped  
2. options \(object, optional\)  
{  
  "confTarget" \(numeric, optional\) Confirmation target \(in blocks\)  
  "totalFee" \(numeric, optional\) Total fee \(NOT feerate\) to pay, in satoshis. In rare cases, the actual fee paid might be slightly higher than the specified totalFee if the tx change output has to be removed because it is too close to the dust threshold.  
"replaceable" \(boolean, optional, default true\) Whether the new transaction should still be marked bip-125 replaceable. If true, the sequence numbers in the transaction will be left unchanged from the original. If false, any input sequence numbers in the original transaction that were less than 0xfffffffe will be increased to 0xfffffffe so the new transaction will not be explicitly bip-125 replaceable \(though it may still be replaceable in practice, for example if it has unconfirmed ancestors which are replaceable\).  
"estimate\_mode" \(string, optional, default=UNSET\) The fee estimate mode, must be one of:  
  "UNSET"  
  "ECONOMICAL"  
  "CONSERVATIVE"  
}  
  
**Result:**  
{  
  "txid": "value", \(string\) The id of the new transaction  
  "origfee": n, \(numeric\) Fee of the replaced transaction  
  "fee": n, \(numeric\) Fee of the new transaction  
  "errors": \[ str... \] \(json array of strings\) Errors encountered during processing \(may be empty\)  
}  
  
**Examples:**  
Bump the fee, get the new transaction's txid  
&gt; nix-cli bumpfee &lt;txid&gt;

`dumpprivkey "address"` Reveals the private key corresponding to 'address'. Then the importprivkey can be used with this output.  
  
**Arguments:**  
1. "address" \(string, required\) The nix address for the private key  
  
**Result:**  
"key" \(string\) The private key  
  
**Examples:**  
&gt; nix-cli dumpprivkey "myaddress"  
&gt; nix-cli importprivkey "mykey"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "dumpprivkey", "params": \["myaddress"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`dumpwalletprivatekeys "filename"` Dumps all wallet keys in a human-readable format to a server-side file. This does not allow overwriting existing files.  
Imported scripts are included in the dumpfile, but corresponding BIP173 addresses, etc. may not be added automatically by importwallet.  
Note that if your wallet contains keys which are not derived from your HD seed \(e.g. imported keys\), these are not covered by only backing up the seed itself, and must be backed up too \(e.g. ensure you back up the whole dumpfile\).  
  
**Arguments:**  
1. "filename" \(string, required\) The filename with path \(either absolute or relative to nixd\)  
  
**Result:**  
{ \(json object\)  
  "filename" : { \(string\) The filename with full absolute path  
}  
  
**Examples:**  
&gt; nix-cli dumpwallet "test"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "dumpwallet", "params": \["test"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`encryptwallet "passphrase"` Encrypts the wallet with 'passphrase'. This is for first time encryption. After this, any calls that interact with private keys such as sending or signing will require the passphrase to be set prior the making these calls. Use the walletpassphrase call for this, and then walletlock call. If the wallet is already encrypted, use the walletpassphrasechange call.  
Note that this will shutdown the server.  
  
**Arguments:**  
1. "passphrase" \(string\) The pass phrase to encrypt the wallet with. It must be at least 1 character, but should be long.  
  
**Examples:**  
Encrypt your wallet  
&gt; nix-cli encryptwallet "my pass phrase"  
Now set the passphrase to use the wallet, such as for signing or sending nix  
&gt; nix-cli walletpassphrase "my pass phrase"  
Now we can do something like sign  
&gt; nix-cli signmessage "address" "test message"  
Now lock the wallet again by removing the passphrase  
&gt; nix-cli walletlock  
As a json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "encryptwallet", "params": \["my pass phrase"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getaccount "address"` DEPRECATED. Returns the account associated with the given address.  
  
**Arguments:**  
1. "address" \(string, required\) The nix address for account lookup.  
  
**Result:**  
"accountname" \(string\) the account address  
  
**Examples:**  
&gt; nix-cli getaccount "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getaccount", "params": \["1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getaccountaddress "account"` DEPRECATED. Returns the current NIX address for receiving payments to this account.  
  
**Arguments:**  
1. "account" \(string, required\) The account name for the address. It can also be set to the empty string "" to represent the default account. The account does not need to exist, it will be created and a new address created if there is no account by the given name.  
  
**Result:**  
"address" \(string\) The account nix address  
  
**Examples:**  
&gt; nix-cli getaccountaddress  
&gt; nix-cli getaccountaddress ""  
&gt; nix-cli getaccountaddress "myaccount"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getaccountaddress", "params": \["myaccount"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getalladdresses` Get all send addresses.

`getbalance ("account" minconf include_watchonly)` If account is not specified, returns the server's total available balance. The available balance is what the wallet considers currently spendable, and is thus affected by options which limit spendability such as -spendzeroconfchange. If account is specified \(DEPRECATED\), returns the balance in the account.  
Note that the account "" is not the same as leaving the parameter out. The server total may be different to the balance in the default "" account.  
  
**Arguments:**  
1. "account" \(string, optional\) DEPRECATED. The account string may be given as a specific account name to find the balance associated with wallet keys in a named account, or as the empty string \(""\) to find the balance associated with wallet keys not in any named account, or as "\*" to find the balance associated with all wallet keys regardless of account. When this option is specified, it calculates the balance in a different way than when it is not specified, and which can count spends twice when there are conflicting pending transactions \(such as those created by the bumpfee command\), temporarily resulting in low or even negative balances. In general, account balance calculation is not considered reliable and has resulted in confusing outcomes, so it is recommended to avoid passing this argument.  
2. minconf \(numeric, optional, default=1\) Only include transactions confirmed at least this many times.  
3. include\_watchonly \(bool, optional, default=false\) Also include balance in watch-only addresses \(see 'importaddress'\)  
  
**Result:**  
amount \(numeric\) The total amount in NIX received for this account.  
  
**Examples:**  
The total amount in the wallet with 1 or more confirmations  
&gt; nix-cli getbalance  
The total amount in the wallet at least 6 blocks confirmed  
&gt; nix-cli getbalance "\*" 6  
As a json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getbalance", "params": \["\*", 6\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getcoldstakinginfo` Returns an object containing coldstaking related information.  
  
**Result:**  
{  
  "enabled": true\|false, \(boolean\) If a valid coldstakingaddress is loaded or not on this wallet.  
  "coldstaking\_address" \(string\) The address of the current coldstakingaddress.  
  "coin\_in\_stakeable\_script" \(numeric\) Current amount of coin in scripts stakeable by this wallet.  
  "coin\_in\_coldstakeable\_script" \(numeric\) Current amount of coin in scripts stakeable by the wallet with the coldstakingaddress.  
  "percent\_in\_coldstakeable\_script" \(numeric\) Percentage of coin in coldstakeable scripts.  
  "currently\_staking" \(numeric\) Amount of coin estimated to be currently staking by this wallet.  
}  
  
**Examples:**  
&gt; nix-cli getcoldstakinginfo  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getcoldstakinginfo", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getfeeforamount "amount" "address"` Returns the fee needed for the amount needed to send.  
  
**Arguments:**  
1. "amount" \(int, required\) The amount you want for fee calculation.  
2. "address" \(string, required\) The address you want to send to for fee calculation.  
  
**Result:**  
"fee" \(json string of fee\)  
  
**Examples:**  
&gt; nix-cli getfeeforamount "400" "ZM72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd"

`getleasestakinglist` Get list of current LPoS contracts in wallet. Requires wallet passphrase to be set with walletpassphrase call.

`getnewaddress ("account" "address_type")` Returns a new NIX address for receiving payments. If 'account' is specified \(DEPRECATED\), it is added to the address book so payments received with the address will be credited to 'account'.  
  
**Arguments:**  
1. "account" \(string, optional\) DEPRECATED. The account name for the address to be linked to. If not provided, the default account "" is used. It can also be set to the empty string "" to represent the default account. The account does not need to exist, it will be created if there is no account by the given name.  
2. "address\_type" \(string, optional\) The address type to use. Options are "ghostnode", "p2sh-segwit\(default\)", and "bech32". Default is set by -addresstype.  
  
**Result:**  
"address" \(string\) The new nix address  
  
**Examples:**  
&gt; nix-cli getnewaddress  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getnewaddress", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getrawchangeaddress ("address_type")` Returns a new NIX address, for receiving change. This is for use with raw transactions, NOT normal use.  
  
**Arguments:**  
1. "address\_type" \(string, optional\) The address type to use. Options are "legacy", "p2sh-segwit", and "bech32". Default is set by -changetype.  
  
**Result:**  
"address" \(string\) The address  
  
**Examples:**  
&gt; nix-cli getrawchangeaddress  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getrawchangeaddress", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getreceivedbyaccount "account" (minconf)` DEPRECATED. Returns the total amount received by addresses with &lt;account&gt; in transactions with at least \[minconf\] confirmations.  
  
**Arguments:**  
1. "account" \(string, required\) The selected account, may be the default account using "".  
2. minconf \(numeric, optional, default=1\) Only include transactions confirmed at least this many times.  
  
**Result:**  
amount \(numeric\) The total amount in NIX received for this account.  
  
**Examples:**  
Amount received by the default account with at least 1 confirmation  
&gt; nix-cli getreceivedbyaccount ""  
Amount received at the tabby account including unconfirmed amounts with zero confirmations  
&gt; nix-cli getreceivedbyaccount "tabby" 0  
The amount with at least 6 confirmations  
&gt; nix-cli getreceivedbyaccount "tabby" 6  
As a json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getreceivedbyaccount", "params": \["tabby", 6\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getreceivedbyaddress "address" (minconf)` Returns the total amount received by the given address in transactions with at least minconf confirmations.  
  
**Arguments:**  
1. "address" \(string, required\) The nix address for transactions.  
2. minconf \(numeric, optional, default=1\) Only include transactions confirmed at least this many times.  
  
**Result:**  
amount \(numeric\) The total amount in NIX received at this address.  
  
**Examples:**  
The amount from transactions with at least 1 confirmation  
&gt; nix-cli getreceivedbyaddress "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX"  
The amount including unconfirmed transactions, zero confirmations  
&gt; nix-cli getreceivedbyaddress "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" 0  
The amount with at least 6 confirmations  
&gt; nix-cli getreceivedbyaddress "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" 6  
As a json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getreceivedbyaddress", "params": \["1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX", 6\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getstakingaverage` Get the average stake amount in the last 500 block sample.

`getstakinginfo` Returns an object containing staking-related information.  
  
**Result:**  
{  
  "enabled": true\|false, \(boolean\) if staking is enabled or not on this wallet  
  "staking": true\|false, \(boolean\) if this wallet is staking or not  
  "errors": "..." \(string\) any error messages  
  "percentyearreward": xxxxxxx, \(numeric\) current stake reward percentage  
  "moneysupply": xxxxxxx, \(numeric\) the total amount of NIX in the network  
  "reserve": xxxxxxx, \(numeric\) the total amount of NIX in the network  
  "walletdonationpercent": xxxxxxx, \(numeric\) user set percentage of the block reward ceded to development  
  "currentblocksize": nnn, \(numeric\) the last block size in bytes  
  "currentblockweight": nnn, \(numeric\) the last block weight  
  "currentblocktx": nnn, \(numeric\) the number of transactions in the last block  
  "pooledtx": n \(numeric\) the number of transactions in the mempool  
  "difficulty": xxx.xxxxx \(numeric\) the current difficulty  
  "lastsearchtime": xxxxxxx \(numeric\) the last time this wallet searched for a coinstake  
  "weight": xxxxxxx \(numeric\) the current stake weight of this wallet  
  "netstakeweight": xxxxxxx \(numeric\) the current stake weight of the network  
  "expectedtime": xxxxxxx \(numeric\) estimated time for next stake  
}  
  
**Examples:**  
&gt; nix-cli getstakinginfo  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getstakinginfo", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`gettransaction "txid" (include_watchonly)` Get detailed information about in-wallet transaction &lt;txid&gt;  
  
**Arguments:**  
1. "txid" \(string, required\) The transaction id  
2. "include\_watchonly" \(bool, optional, default=false\) Whether to include watch-only addresses in balance calculation and details\[\]  
  
**Result:**  
{  
  "amount" : x.xxx, \(numeric\) The transaction amount in NIX  
  "fee": x.xxx, \(numeric\) The amount of the fee in NIX. This is negative and only available for the 'send' category of transactions.  
  "confirmations" : n, \(numeric\) The number of confirmations  
  "blockhash" : "hash", \(string\) The block hash  
  "blockindex" : xx, \(numeric\) The index of the transaction in the block that includes it  
  "blocktime" : ttt, \(numeric\) The time in seconds since epoch \(1 Jan 1970 GMT\)  
  "txid" : "transactionid", \(string\) The transaction id.  
  "time" : ttt, \(numeric\) The transaction time in seconds since epoch \(1 Jan 1970 GMT\)  
  "timereceived" : ttt, \(numeric\) The time received in seconds since epoch \(1 Jan 1970 GMT\)  
  "bip125-replaceable": "yes\|no\|unknown", \(string\) Whether this transaction could be replaced due to BIP125 \(replace-by-fee\); may be unknown for unconfirmed transactions not in the mempool  
 "details" : \[  
  {  
    "account" : "accountname", \(string\) DEPRECATED. The account name involved in the transaction, can be "" for the default account.  
    "address" : "address", \(string\) The nix address involved in the transaction  
    "category" : "send\|receive", \(string\) The category, either 'send' or 'receive'  
    "amount" : x.xxx, \(numeric\) The amount in NIX  
    "label" : "label", \(string\) A comment for the address/transaction, if any  
    "vout" : n, \(numeric\) the vout value  
    "fee": x.xxx, \(numeric\) The amount of the fee in NIX. This is negative and only available for the 'send' category of transactions.  
    "abandoned": xxx \(bool\) 'true' if the transaction has been abandoned \(inputs are respendable\). Only available for the 'send' category of transactions.  
  }  
  ,...  
  \],  
  "hex" : "data" \(string\) Raw data for transaction  
}  
  
**Examples:**  
&gt; nix-cli gettransaction "1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5fbf5d48d"  
&gt; nix-cli gettransaction "1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5fbf5d48d" true  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "gettransaction", "params": \["1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5fbf5d48d"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`getunconfirmedbalance` Returns the server's total unconfirmed balance

`getwalletinfo` Returns an object containing various wallet state info.  
  
**Result:**  
{  
  "walletname": xxxxx, \(string\) the wallet name  
  "walletversion": xxxxx, \(numeric\) the wallet version  
  "balance": xxxxxxx, \(numeric\) the total confirmed balance of the wallet in NIX  
  "unconfirmed\_balance": xxx, \(numeric\) the total unconfirmed balance of the wallet in NIX  
  "immature\_balance": xxxxxx, \(numeric\) the total immature balance of the wallet in NIX  
  "txcount": xxxxxxx, \(numeric\) the total number of transactions in the wallet  
  "keypoololdest": xxxxxx, \(numeric\) the timestamp \(seconds since Unix epoch\) of the oldest pre-generated key in the key pool  
  "keypoolsize": xxxx, \(numeric\) how many new keys are pre-generated \(only counts external keys\)  
  "keypoolsize\_hd\_internal": xxxx, \(numeric\) how many new keys are pre-generated for internal use \(used for change outputs, only appears if the wallet is using this feature, otherwise external keys are used\)  
  "unlocked\_until": ttt, \(numeric\) the timestamp in seconds since epoch \(midnight Jan 1 1970 GMT\) that the wallet is unlocked for transfers, or 0 if the wallet is locked  
  "paytxfee": x.xxxx, \(numeric\) the transaction fee configuration, set in NIX/kB  
  "hdmasterkeyid": "&lt;hash160&gt;" \(string, optional\) the Hash160 of the HD master pubkey \(only present when HD is enabled\)  
}  
  
**Examples:**  
&gt; nix-cli getwalletinfo  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getwalletinfo", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`importaddress "address" ("label" rescan p2sh)` Adds a script \(in hex\) or address that can be watched as if it were in your wallet but cannot be used to spend. Requires a new wallet backup.  
  
**Arguments:**  
1. "script" \(string, required\) The hex-encoded script \(or address\)  
2. "label" \(string, optional, default=""\) An optional label  
3. rescan \(boolean, optional, default=true\) Rescan the wallet for transactions  
4. p2sh \(boolean, optional, default=false\) Add the P2SH version of the script as well  
Note: This call can take minutes to complete if rescan is true, during that time, other rpc calls may report that the imported address exists but related transactions are still missing, leading to temporarily incorrect/bogus balances and unspent outputs until rescan completes. If you have the full public key, you should call importpubkey instead of this.  
Note: If you import a non-standard raw script in hex form, outputs sending to it will be treated as change, and not show up in many RPCs.  
  
**Examples:**  
Import a script with rescan  
&gt; nix-cli importaddress "myscript"  
Import using a label without rescan  
&gt; nix-cli importaddress "myscript" "testing" false  
As a JSON-RPC call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "importaddress", "params": \["myscript", "testing", false\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`importmulti "requests" ("options")` Import addresses/scripts \(with private or public keys, redeem script \(P2SH\)\), rescanning all addresses in one-shot-only \(rescan can be disabled via options\). Requires a new wallet backup.  
  
**Arguments:**  
1. requests \(array, required\) Data to be imported  
\[ \(array of json objects\)  
{  
  "scriptPubKey": "&lt;script&gt;" \| { "address":"&lt;address&gt;" }, \(string / json, required\) Type of scriptPubKey \(string for script, json for address\)  
  "timestamp": timestamp \| "now" , \(integer / string, required\) Creation time of the key in seconds since epoch \(Jan 1 1970 GMT\), or the string "now" to substitute the current synced blockchain time. The timestamp of the oldest key will determine how far back blockchain rescans need to begin for missing wallet transactions. "now" can be specified to bypass scanning, for keys which are known to never have been used, and 0 can be specified to scan the entire blockchain. Blocks up to 2 hours before the earliest key creation time of all keys being imported by the importmulti call will be scanned.  
  "redeemscript": "&lt;script&gt;" , \(string, optional\) Allowed only if the scriptPubKey is a P2SH address or a P2SH scriptPubKey  
  "pubkeys": \["&lt;pubKey&gt;", ... \] , \(array, optional\) Array of strings giving pubkeys that must occur in the output or redeemscript  
  "keys": \["&lt;key&gt;", ... \] , \(array, optional\) Array of strings giving private keys whose corresponding public keys must occur in the output or redeemscript  
  "internal": &lt;true&gt; , \(boolean, optional, default: false\) Stating whether matching outputs should be treated as not incoming payments  
  "watchonly": &lt;true&gt; , \(boolean, optional, default: false\) Stating whether matching outputs should be considered watched even when they're not spendable, only allowed if keys are empty  
  "label": &lt;label&gt; , \(string, optional, default: ''\) Label to assign to the address \(aka account name, for now\), only allowed with internal=false  
}  
,...  
\]  
2. options \(json, optional\)  
{  
  "rescan": &lt;false&gt;, \(boolean, optional, default: true\) Stating if should rescan the blockchain after all imports  
}  
Note: This call can take minutes to complete if rescan is true, during that time, other rpc calls may report that the imported keys, addresses or scripts exists but related transactions are still missing.  
  
**Examples:**  
&gt; nix-cli importmulti '\[{ "scriptPubKey": { "address": "&lt;my address&gt;" }, "timestamp":1455191478 }, { "scriptPubKey": { "address": "&lt;my 2nd address&gt;" }, "label": "example 2", "timestamp": 1455191480 }\]'  
&gt; nix-cli importmulti '\[{ "scriptPubKey": { "address": "&lt;my address&gt;" }, "timestamp":1455191478 }\]' '{ "rescan": false}'  
Response is an array with the same size as the input that has the execution result :  
\[{ "success": true } , { "success": false, "error": { "code": -1, "message": "Internal Server Error"} }, ... \]

`importprivkey "privkey" ("label") (rescan)` Adds a private key \(as returned by dumpprivkey\) to your wallet. Requires a new wallet backup.  
  
Arguments:  
1. "privkey" \(string, required\) The private key \(see dumpprivkey\)  
2. "label" \(string, optional, default=""\) An optional label  
3. rescan \(boolean, optional, default=true\) Rescan the wallet for transactions  
Note: This call can take minutes to complete if rescan is true, during that time, other rpc calls may report that the imported key exists but related transactions are still missing, leading to temporarily incorrect/bogus balances and unspent outputs until rescan completes.  
  
Examples:  
Dump a private key  
&gt; nix-cli dumpprivkey "myaddress"  
Import the private key with rescan  
&gt; nix-cli importprivkey "mykey"  
Import using a label and without rescan  
&gt; nix-cli importprivkey "mykey" "testing" false  
Import using default blank label and without rescan  
&gt; nix-cli importprivkey "mykey" "" false  
As a JSON-RPC call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "importprivkey", "params": \["mykey", "testing", false\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`importprunedfunds` Imports funds without rescan. Corresponding address or script must previously be included in wallet. Aimed towards pruned wallets. The end-user is responsible to import additional transactions that subsequently spend the imported outputs or rescan after the point in the blockchain the transaction is included.  
  
**Arguments:**  
1. "rawtransaction" \(string, required\) A raw transaction in hex funding an already-existing address in wallet  
2. "txoutproof" \(string, required\) The hex output from gettxoutproof that contains the transaction

`importpubkey "pubkey" ("label" rescan)` Adds a public key \(in hex\) that can be watched as if it were in your wallet but cannot be used to spend. Requires a new wallet backup.  
  
**Arguments:**  
1. "pubkey" \(string, required\) The hex-encoded public key  
2. "label" \(string, optional, default=""\) An optional label  
3. rescan \(boolean, optional, default=true\) Rescan the wallet for transactions  
Note: This call can take minutes to complete if rescan is true, during that time, other rpc calls may report that the imported pubkey exists but related transactions are still missing, leading to temporarily incorrect/bogus balances and unspent outputs until rescan completes.  
  
**Examples:**  
Import a public key with rescan  
&gt; nix-cli importpubkey "mypubkey"  
Import using a label without rescan  
&gt; nix-cli importpubkey "mypubkey" "testing" false  
As a JSON-RPC call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "importpubkey", "params": \["mypubkey", "testing", false\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`importwallet "filename"` Imports keys from a wallet dump file \(see dumpwallet\). Requires a new wallet backup to include imported keys.  
  
**Arguments:**  
1. "filename" \(string, required\) The wallet file  
  
**Examples:**  
Dump the wallet  
&gt; nix-cli dumpwallet "test"  
Import the wallet  
&gt; nix-cli importwallet "test"  
Import using the json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "importwallet", "params": \["test"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`keypoolrefill (newsize)` Fills the keypool. Requires wallet passphrase to be set with walletpassphrase call.  
  
**Arguments:**  
1. newsize \(numeric, optional, default=100\) The new keypool size  
  
**Examples:**  
&gt; nix-cli keypoolrefill  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "keypoolrefill", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`leasestaking "address" amount ("comment" "comment_to" subtractfeefromamount replaceable conf_target "estimate_mode")` Lease an amount of nix to a certain address to stake. Requires wallet passphrase to be set with walletpassphrase call.  
  
**Arguments:**  
1. "lease address" \(string, required\) The nix address to lease stakes to.  
2. "amount" \(numeric or string, required\) The amount in NIX to send. eg 0.1  
3. "fee percent" \(numeric, optional\) The percentage to allow delegator to take. eg 11.9 \(11.9%\)  
4. "lease percent reward address" \(string, optional\) The nix address to force lease fee stakes to.  
5. "comment" \(string, optional\) A comment used to store what the transaction is for. This is not part of the transaction, just kept in your wallet.  
6. "comment\_to" \(string, optional\) A comment to store the name of the person or organization to which you're sending the transaction. This is not part of the transaction, just kept in your wallet.  
7. subtractfeefromamount \(boolean, optional, default=false\) The fee will be deducted from the amount being sent. The recipient will receive less nix than you enter in the amount field.  
8. replaceable \(boolean, optional\) Allow this transaction to be replaced by a transaction with higher fees via BIP 125  
9. conf\_target \(numeric, optional\) Confirmation target \(in blocks\)  
10. "estimate\_mode" \(string, optional, default=UNSET\) The fee estimate mode, must be one of:  
 "UNSET"  
 "ECONOMICAL"  
 "CONSERVATIVE"  
  
**Result:**  
"txid" \(string\) The transaction id.  
  
**Examples:**  
&gt; nix-cli leasestaking "Nf72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 150  
&gt; nix-cli leasestaking "Nf72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 150 11.9 "NG72Sfpbz1BLpXFHz9m3CdqATR44JDaydd"

`listaccounts (minconf include_watchonly)` DEPRECATED. Returns Object that has account names as keys, account balances as values.  
  
**Arguments:**  
1. minconf \(numeric, optional, default=1\) Only include transactions with at least this many confirmations  
2. include\_watchonly \(bool, optional, default=false\) Include balances in watch-only addresses \(see 'importaddress'\)  
  
**Result:**  
{ \(json object where keys are account names, and values are numeric balances  
  "account": x.xxx, \(numeric\) The property name is the account name, and the value is the total balance for the account.  
  ...  
}  
  
**Examples:**  
List account balances where there at least 1 confirmation  
&gt; nix-cli listaccounts  
List account balances including zero confirmation transactions  
&gt; nix-cli listaccounts 0  
List account balances for 6 or more confirmations  
&gt; nix-cli listaccounts 6  
As json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listaccounts", "params": \[6\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`listaddressgroupings` Lists groups of addresses which have had their common ownership made public by common use as inputs or as the resulting change in past transactions.  
  
**Result:**  
\[  
  \[  
    \[  
      "address", \(string\) The nix address amount, \(numeric\) The amount in NIX  
      "account" \(string, optional\) DEPRECATED. The account  
    \]  
    ,...  
  \]  
  ,...  
\]  
  
**Examples:**  
&gt; nix-cli listaddressgroupings  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listaddressgroupings", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`listlockunspent` Returns list of temporarily unspendable outputs. See the lockunspent call to lock and unlock transactions for spending.  
  
**Result:**  
\[  
  {  
    "txid" : "transactionid", \(string\) The transaction id locked  
    "vout" : n \(numeric\) The vout value  
  }  
  ,...  
\]  
  
**Examples:**  
List the unspent transactions  
&gt; nix-cli listunspent  
Lock an unspent transaction  
&gt; nix-cli lockunspent false "\[{\"txid\":\"a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0\",\"vout\":1}\]"  
List the locked transactions  
&gt; nix-cli listlockunspent  
Unlock the transaction again  
&gt; nix-cli lockunspent true "\[{\"txid\":\"a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0\",\"vout\":1}\]"  
As a json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listlockunspent", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`listreceivedbyaccount (minconf include_empty include_watchonly)` DEPRECATED. List balances by account.  
  
**Arguments:**  
1. minconf \(numeric, optional, default=1\) The minimum number of confirmations before payments are included.  
2. include\_empty \(bool, optional, default=false\) Whether to include accounts that haven't received any payments.  
3. include\_watchonly \(bool, optional, default=false\) Whether to include watch-only addresses \(see 'importaddress'\).  
  
**Result:**  
\[  
  {  
    "involvesWatchonly" : true, \(bool\) Only returned if imported addresses were involved in transaction  
    "account" : "accountname", \(string\) The account name of the receiving account  
    "amount" : x.xxx, \(numeric\) The total amount received by addresses with this account  
    "confirmations" : n, \(numeric\) The number of confirmations of the most recent transaction included  
    "label" : "label" \(string\) A comment for the address/transaction, if any  
  }  
  ,...  
\]  
  
**Examples:**  
&gt; nix-cli listreceivedbyaccount  
&gt; nix-cli listreceivedbyaccount 6 true  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listreceivedbyaccount", "params": \[6, true, true\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`listreceivedbyaddress (minconf include_empty include_watchonly)` List balances by receiving address.  
  
**Arguments:**  
1. minconf \(numeric, optional, default=1\) The minimum number of confirmations before payments are included.  
2. include\_empty \(bool, optional, default=false\) Whether to include addresses that haven't received any payments.  
3. include\_watchonly \(bool, optional, default=false\) Whether to include watch-only addresses \(see 'importaddress'\).  
  
**Result:**  
\[  
  {  
    "involvesWatchonly" : true, \(bool\) Only returned if imported addresses were involved in transaction  
    "address" : "receivingaddress", \(string\) The receiving address  
    "account" : "accountname", \(string\) DEPRECATED. The account of the receiving address. The default account is "".  
    "amount" : x.xxx, \(numeric\) The total amount in NIX received by the address  
    "confirmations" : n, \(numeric\) The number of confirmations of the most recent transaction included  
    "label" : "label", \(string\) A comment for the address/transaction, if any  
    "txids": \[  
    n, \(numeric\) The ids of transactions received with the address  
    ...  
  \]  
}  
,...  
\]  
  
**Examples:**  
&gt; nix-cli listreceivedbyaddress  
&gt; nix-cli listreceivedbyaddress 6 true  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listreceivedbyaddress", "params": \[6, true, true\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`listsinceblock ("blockhash" target_confirmations include_watchonly include_removed)` Get all transactions in blocks since block \[blockhash\], or all transactions if omitted. If "blockhash" is no longer a part of the main chain, transactions from the fork point onward are included.  
Additionally, if include\_removed is set, transactions affecting the wallet which were removed are returned in the "removed" array.  
  
**Arguments:**  
1. "blockhash" \(string, optional\) The block hash to list transactions since  
2. target\_confirmations: \(numeric, optional, default=1\) Return the nth block hash from the main chain. e.g. 1 would mean the best block hash. Note: this is not used as a filter, but only affects \[lastblock\] in the return value  
3. include\_watchonly: \(bool, optional, default=false\) Include transactions to watch-only addresses \(see 'importaddress'\)  
4. include\_removed: \(bool, optional, default=true\) Show transactions that were removed due to a reorg in the "removed" array  
\(not guaranteed to work on pruned nodes\)  
  
**Result:**  
{  
  "transactions": \[  
  "account":"accountname", \(string\) DEPRECATED. The account name associated with the transaction. Will be "" for the default account.  
  "address":"address", \(string\) The nix address of the transaction. Not present for move transactions \(category = move\).  
  "category":"send\|receive", \(string\) The transaction category. 'send' has negative amounts, 'receive' has positive amounts.  
  "amount": x.xxx, \(numeric\) The amount in NIX. This is negative for the 'send' category, and for the 'move' category for moves outbound. It is positive for the 'receive' category, and for the 'move' category for inbound funds.  
  "vout" : n, \(numeric\) the vout value  
  "fee": x.xxx, \(numeric\) The amount of the fee in NIX. This is negative and only available for the 'send' category of transactions.  
  "confirmations": n, \(numeric\) The number of confirmations for the transaction. Available for 'send' and 'receive' category of transactions. When it's &lt; 0, it means the transaction conflicted that many blocks ago.  
  "blockhash": "hashvalue", \(string\) The block hash containing the transaction. Available for 'send' and 'receive' category of transactions.  
  "blockindex": n, \(numeric\) The index of the transaction in the block that includes it. Available for 'send' and 'receive' category of transactions.  
  "blocktime": xxx, \(numeric\) The block time in seconds since epoch \(1 Jan 1970 GMT\).  
  "txid": "transactionid", \(string\) The transaction id. Available for 'send' and 'receive' category of transactions.  
  "time": xxx, \(numeric\) The transaction time in seconds since epoch \(Jan 1 1970 GMT\).  
  "timereceived": xxx, \(numeric\) The time received in seconds since epoch \(Jan 1 1970 GMT\). Available for 'send' and 'receive' category of transactions.  
  "bip125-replaceable": "yes\|no\|unknown", \(string\) Whether this transaction could be replaced due to BIP125 \(replace-by-fee\); may be unknown for unconfirmed transactions not in the mempool  
  "abandoned": xxx, \(bool\) 'true' if the transaction has been abandoned \(inputs are respendable\). Only available for the 'send' category of transactions.  
  "comment": "...", \(string\) If a comment is associated with the transaction.  
  "label" : "label" \(string\) A comment for the address/transaction, if any  
  "to": "...", \(string\) If a comment to is associated with the transaction.  
  \],  
  "removed": \[  
  &lt;structure is the same as "transactions" above, only present if include\_removed=true&gt;  
Note: transactions that were readded in the active chain will appear as-is in this array, and may thus have a positive confirmation count.  
  \],  
  "lastblock": "lastblockhash" \(string\) The hash of the block \(target\_confirmations-1\) from the best block on the main chain. This is typically used to feed back into listsinceblock the next time you call it. So you would generally use a target\_confirmations of say 6, so you will be continually re-notified of transactions until they've reached 6 confirmations plus any new ones  
}  
  
**Examples:**  
&gt; nix-cli listsinceblock  
&gt; nix-cli listsinceblock "000000000000000bacf66f7497b7dc45ef753ee9a7d38571037cdb1a57f663ad" 6  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listsinceblock", "params": \["000000000000000bacf66f7497b7dc45ef753ee9a7d38571037cdb1a57f663ad", 6\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`listtransactions ("account" count skip include_watchonly)` Returns up to 'count' most recent transactions skipping the first 'from' transactions for account 'account'.  
  
**Arguments:**  
1. "account" \(string, optional\) DEPRECATED. The account name. Should be "\*".  
2. count \(numeric, optional, default=10\) The number of transactions to return  
3. skip \(numeric, optional, default=0\) The number of transactions to skip  
4. include\_watchonly \(bool, optional, default=false\) Include transactions to watch-only addresses \(see 'importaddress'\)  
  
**Result:**  
\[  
  {  
    "account":"accountname", \(string\) DEPRECATED. The account name associated with the transaction. It will be "" for the default account.  
    "address":"address", \(string\) The nix address of the transaction. Not present for move transactions \(category = move\).  
    "category":"send\|receive\|move", \(string\) The transaction category. 'move' is a local \(off blockchain\) transaction between accounts, and not associated with an address, transaction id or block. 'send' and 'receive' transactions are associated with an address, transaction id and block details  
    "amount": x.xxx, \(numeric\) The amount in NIX. This is negative for the 'send' category, and for the 'move' category for moves outbound. It is positive for the 'receive' category, and for the 'move' category for inbound funds.  
    "label": "label", \(string\) A comment for the address/transaction, if any  
    "vout": n, \(numeric\) the vout value  
    "fee": x.xxx, \(numeric\) The amount of the fee in NIX. This is negative and only available for the 'send' category of transactions.  
    "confirmations": n, \(numeric\) The number of confirmations for the transaction. Available for 'send' and 'receive' category of transactions. Negative confirmations indicate the transaction conflicts with the block chain  
    "trusted": xxx, \(bool\) Whether we consider the outputs of this unconfirmed transaction safe to spend.  
    "blockhash": "hashvalue", \(string\) The block hash containing the transaction. Available for 'send' and 'receive' category of transactions.  
    "blockindex": n, \(numeric\) The index of the transaction in the block that includes it. Available for 'send' and 'receive' category of transactions.  
    "blocktime": xxx, \(numeric\) The block time in seconds since epoch \(1 Jan 1970 GMT\).  
    "txid": "transactionid", \(string\) The transaction id. Available for 'send' and 'receive' category of transactions.  
    "time": xxx, \(numeric\) The transaction time in seconds since epoch \(midnight Jan 1 1970 GMT\).  
    "timereceived": xxx, \(numeric\) The time received in seconds since epoch \(midnight Jan 1 1970 GMT\). Available for 'send' and 'receive' category of transactions.  
    "comment": "...", \(string\) If a comment is associated with the transaction.  
    "otheraccount": "accountname", \(string\) DEPRECATED. For the 'move' category of transactions, the account the funds came from \(for receiving funds, positive amounts\), or went to \(for sending funds, negative amounts\).  
    "bip125-replaceable": "yes\|no\|unknown", \(string\) Whether this transaction could be replaced due to BIP125 \(replace-by-fee\); may be unknown for unconfirmed transactions not in the mempool  
    "abandoned": xxx \(bool\) 'true' if the transaction has been abandoned \(inputs are respendable\). Only available for the 'send' category of transactions.  
  }  
\]  
  
**Examples:**  
List the most recent 10 transactions in the systems  
&gt; nix-cli listtransactions  
List transactions 100 to 120  
&gt; nix-cli listtransactions "\*" 20 100  
As a json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listtransactions", "params": \["\*", 20, 100\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`listunspent (minconf maxconf ["addresses",...] [include_unsafe] [query_options])` Returns array of unspent transaction outputs with between minconf and maxconf \(inclusive\) confirmations. Optionally filter to only include txouts paid to specified addresses.  
  
**Arguments:**  
1. minconf \(numeric, optional, default=1\) The minimum confirmations to filter  
2. maxconf \(numeric, optional, default=9999999\) The maximum confirmations to filter  
3. "addresses" \(string\) A json array of nix addresses to filter  
\[  
  "address" \(string\) nix address  
  ,...  
\]  
4. include\_unsafe \(bool, optional, default=true\) Include outputs that are not safe to spend See description of "safe" attribute below.  
5. query\_options \(json, optional\) JSON with query options  
{  
  "minimumAmount" \(numeric or string, default=0\) Minimum value of each UTXO in NIX  
 "maximumAmount" \(numeric or string, default=unlimited\) Maximum value of each UTXO in NIX  
 "maximumCount" \(numeric or string, default=unlimited\) Maximum number of UTXOs  
 "minimumSumAmount" \(numeric or string, default=unlimited\) Minimum sum value of all UTXOs in NIX  
}  
  
**Result:**  
\[ \(array of json object\)  
  {  
    "txid" : "txid", \(string\) the transaction id  
    "vout" : n, \(numeric\) the vout value  
    "address" : "address", \(string\) the nix address  
    "account" : "account", \(string\) DEPRECATED. The associated account, or "" for the default account  
    "scriptPubKey" : "key", \(string\) the script key  
    "amount" : x.xxx, \(numeric\) the transaction output amount in NIX  
    "confirmations" : n, \(numeric\) The number of confirmations  
    "redeemScript" : n \(string\) The redeemScript if scriptPubKey is P2SH  
    "spendable" : xxx, \(bool\) Whether we have the private keys to spend this output  
    "solvable" : xxx, \(bool\) Whether we know how to spend this output, ignoring the lack of keys  
    "safe" : xxx \(bool\) Whether this output is considered safe to spend. Unconfirmed transactions from outside keys and unconfirmed replacement transactions are considered unsafe and are not eligible for spending by fundrawtransaction and sendtoaddress.  
  }  
  ,...  
\]  
  
**Examples:**  
&gt; nix-cli listunspent  
&gt; nix-cli listunspent 6 9999999 "\[\"1PGFqEzfmQch1gKD3ra4k18PNj3tTUUSqg\",\"1LtvqCaApEdUGFkpKMM4MstjcaL4dKg8SP\"\]"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listunspent", "params": \[6, 9999999 "\[\"1PGFqEzfmQch1gKD3ra4k18PNj3tTUUSqg\",\"1LtvqCaApEdUGFkpKMM4MstjcaL4dKg8SP\"\]"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  
&gt; nix-cli listunspent 6 9999999 '\[\]' true '{ "minimumAmount": 0.005 }'  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listunspent", "params": \[6, 9999999, \[\] , true, { "minimumAmount": 0.005 } \] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`listwallets` Returns a list of currently loaded wallets. For full information on the wallet, use "getwalletinfo"  
  
**Result:**  
\[ \(json array of strings\)  
  "walletname" \(string\) the wallet name  
  ...  
\]  
  
**Examples:**  
&gt; nix-cli listwallets  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listwallets", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`lockunspent unlock ([{"txid":"txid","vout":n},...])` Updates list of temporarily unspendable outputs. Temporarily lock \(unlock=false\) or unlock \(unlock=true\) specified transaction outputs. If no transaction outputs are specified when unlocking then all current locked transaction outputs are unlocked. A locked transaction output will not be chosen by automatic coin selection, when spending nix. Locks are stored in memory only. Nodes start with zero locked outputs, and the locked output list is always cleared \(by virtue of process exit\) when a node stops or fails. Also see the listunspent call.  
  
**Arguments:**  
1. unlock \(boolean, required\) Whether to unlock \(true\) or lock \(false\) the specified transactions  
2. "transactions" \(string, optional\) A json array of objects. Each object the txid \(string\) vout \(numeric\)  
\[ \(json array of json objects\)  
  {  
    "txid":"id", \(string\) The transaction id  
    "vout": n \(numeric\) The output number  
  }  
  ,...  
\]  
  
**Result:**  
true\|false \(boolean\) Whether the command was successful or not  
Examples:  
List the unspent transactions  
&gt; nix-cli listunspent  
Lock an unspent transaction  
&gt; nix-cli lockunspent false "\[{\"txid\":\"a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0\",\"vout\":1}\]"  
List the locked transactions  
&gt; nix-cli listlockunspent  
Unlock the transaction again  
&gt; nix-cli lockunspent true "\[{\"txid\":\"a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0\",\"vout\":1}\]"  
As a json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "lockunspent", "params": \[false, "\[{\"txid\":\"a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0\",\"vout\":1}\]"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

`manageaddressbook "action" "address" ("label" "purpose")` Manage the address book.  
  
**Arguments:**  
1. "action" \(string, required\) 'add/edit/del/info/newsend' The action to take.  
2. "address" \(string, required\) The address to affect.  
3. "label" \(string, optional\) Optional label.  
4. "purpose" \(string, optional\) Optional purpose label.  


`move "fromaccount" "toaccount" amount (minconf "comment")` DEPRECATED. Move a specified amount from one account in your wallet to another.  
  
**Arguments:**  
1. "fromaccount" \(string, required\) The name of the account to move funds from. May be the default account using "".  
2. "toaccount" \(string, required\) The name of the account to move funds to. May be the default account using "".  
3. amount \(numeric\) Quantity of NIX to move between accounts.  
4. \(dummy\) \(numeric, optional\) Ignored. Remains for backward compatibility.  
5. "comment" \(string, optional\) An optional comment, stored in the wallet only.  
  
**Result:**  
true\|false \(boolean\) true if successful.  
Examples:  
Move 0.01 NIX from the default account to the account named tabby  
&gt; nix-cli move "" "tabby" 0.01  
Move 0.01 NIX timotei to akiko with a comment and funds have 6 confirmations  
&gt; nix-cli move "timotei" "akiko" 0.01 6 "happy birthday!"  
As a json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "move", "params": \["timotei", "akiko", 0.01, 6, "happy birthday!"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  


`removeprunedfunds "txid"` Deletes the specified transaction from the wallet. Meant for use with pruned wallets and as a companion to importprunedfunds. This will affect wallet balances.  
  
**Arguments:**  
1. "txid" \(string, required\) The hex-encoded id of the transaction you are deleting  
  
**Examples:**  
&gt; nix-cli removeprunedfunds "a8d0c0184dde994a09ec054286f1ce581bebf46446a512166eae7628734ea0a5"  
As a JSON-RPC call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "removeprunedfunds", "params": \["a8d0c0184dde994a09ec054286f1ce581bebf46446a512166eae7628734ea0a5"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  


`rescanblockchain ("start_height") ("stop_height")` Rescan the local blockchain for wallet related transactions.  
  
**Arguments:**  
1. "start\_height" \(numeric, optional\) block height where the rescan should start  
2. "stop\_height" \(numeric, optional\) the last block height that should be scanned  
  
**Result:**  
{  
  "start\_height" \(numeric\) The block height where the rescan has started. If omitted, rescan started from the genesis block.  
  "stop\_height" \(numeric\) The height of the last rescanned block. If omitted, rescan stopped at the chain tip.  
}  
  
**Examples:**  
&gt; nix-cli rescanblockchain 100000 120000  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "rescanblockchain", "params": \[100000, 120000\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  
p, li { white-space: pre-wrap; }  


`reservebalance reserve (amount)` Reserve is true or false to turn balance reserve on or off. Amount is a real and rounded to cent. Set reserve amount not participating in network protection. If no parameters provided current setting is printed. Wallet must be unlocked to modify.  


`sendfrom "fromaccount" "toaddress" amount (minconf "comment" "comment_to")` DEPRECATED \(use sendtoaddress\). Sent an amount from an account to a nix address. Requires wallet passphrase to be set with walletpassphrase call.  
  
**Arguments:**  
1. "fromaccount" \(string, required\) The name of the account to send funds from. May be the default account using "". Specifying an account does not influence coin selection, but it does associate the newly created transaction with the account, so the account's balance computation and transaction history can reflect the spend.  
2. "toaddress" \(string, required\) The nix address to send funds to.  
3. amount \(numeric or string, required\) The amount in NIX \(transaction fee is added on top\).  
4. minconf \(numeric, optional, default=1\) Only use funds with at least this many confirmations.  
5. "comment" \(string, optional\) A comment used to store what the transaction is for. This is not part of the transaction, just kept in your wallet.  
6. "comment\_to" \(string, optional\) An optional comment to store the name of the person or organization to which you're sending the transaction. This is not part of the transaction, it is just kept in your wallet.  
  
**Result:**  
"txid" \(string\) The transaction id.  
  
**Examples:**  
Send 0.01 NIX from the default account to the address, must have at least 1 confirmation  
&gt; nix-cli sendfrom "" "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 0.01  
Send 0.01 from the tabby account to the given address, funds must have at least 6 confirmations  
&gt; nix-cli sendfrom "tabby" "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 0.01 6 "donation" "seans outpost"  
As a json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "sendfrom", "params": \["tabby", "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd", 0.01, 6, "donation", "seans outpost"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  


`sendmany "fromaccount" {"address":amount,...} ( minconf "comment" ["address",...] replaceable conf_target "estimate_mode")` Send multiple times. Amounts are double-precision floating point numbers. Requires wallet passphrase to be set with walletpassphrase call.  
  
**Arguments:**  
1. "fromaccount" \(string, required\) DEPRECATED. The account to send the funds from. Should be "" for the default account  
2. "amounts" \(string, required\) A json object with addresses and amounts  
{  
  "address":amount \(numeric or string\) The nix address is the key, the numeric amount \(can be string\) in NIX is the value  
  ,...  
}  
3. minconf \(numeric, optional, default=1\) Only use the balance confirmed at least this many times.  
4. "comment" \(string, optional\) A comment  
5. subtractfeefrom \(array, optional\) A json array with addresses. The fee will be equally deducted from the amount of each selected address. Those recipients will receive less nix than you enter in their corresponding amount field. If no addresses are specified here, the sender pays the fee.  
  \[  
    "address" \(string\) Subtract fee from this address  
    ,...  
  \]  
6. replaceable \(boolean, optional\) Allow this transaction to be replaced by a transaction with higher fees via BIP 125  
7. conf\_target \(numeric, optional\) Confirmation target \(in blocks\)  
8. "estimate\_mode" \(string, optional, default=UNSET\) The fee estimate mode, must be one of:  
 "UNSET"  
 "ECONOMICAL"  
 "CONSERVATIVE"  
  
**Result:**  
"txid" \(string\) The transaction id for the send. Only 1 transaction is created regardless of the number of addresses.  
  
**Examples:**  
Send two amounts to two different addresses:  
&gt; nix-cli sendmany "" "{\"1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX\":0.01,\"1353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz\":0.02}"  
Send two amounts to two different addresses setting the confirmation and comment:  
&gt; nix-cli sendmany "" "{\"1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX\":0.01,\"1353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz\":0.02}" 6 "testing"  
Send two amounts to two different addresses, subtract fee from amount:  
&gt; nix-cli sendmany "" "{\"1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX\":0.01,\"1353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz\":0.02}" 1 "" "\[\"1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX\",\"1353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz\"\]"  
As a json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "sendmany", "params": \["", {"1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX":0.01,"1353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz":0.02}, 6, "testing"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  


`sendtoaddress "address" amount ("comment" "comment_to" subtractfeefromamount replaceable conf_target "estimate_mode")` Send an amount to a given address. Requires wallet passphrase to be set with walletpassphrase call.  
  
**Arguments:**  
1. "address" \(string, required\) The nix address to send to.  
2. "amount" \(numeric or string, required\) The amount in NIX to send. eg 0.1  
3. "comment" \(string, optional\) A comment used to store what the transaction is for. This is not part of the transaction, just kept in your wallet.  
4. "comment\_to" \(string, optional\) A comment to store the name of the person or organization to which you're sending the transaction. This is not part of the transaction, just kept in your wallet.  
5. subtractfeefromamount \(boolean, optional, default=false\) The fee will be deducted from the amount being sent. The recipient will receive less nix than you enter in the amount field.  
6. replaceable \(boolean, optional\) Allow this transaction to be replaced by a transaction with higher fees via BIP 125  
7. conf\_target \(numeric, optional\) Confirmation target \(in blocks\)  
8. "estimate\_mode" \(string, optional, default=UNSET\) The fee estimate mode, must be one of:  
 "UNSET"  
 "ECONOMICAL"  
 "CONSERVATIVE"  
  
**Result:**  
"txid" \(string\) The transaction id.  
  
**Examples:**  
&gt; nix-cli sendtoaddress "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 0.1  
&gt; nix-cli sendtoaddress "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 0.1 "donation" "seans outpost"  
&gt; nix-cli sendtoaddress "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 0.1 "" "" true  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "sendtoaddress", "params": \["1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd", 0.1, "donation", "seans outpost"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  


`setaccount "address" "account"` DEPRECATED. Sets the account associated with the given address.  
  
**Arguments:**  
1. "address" \(string, required\) The nix address to be associated with an account.  
2. "account" \(string, required\) The account to assign the address to.  
  
**Examples:**  
&gt; nix-cli setaccount "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "tabby"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "setaccount", "params": \["1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX", "tabby"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  


`settxfee <amount>` Set the transaction fee per kB. Overwrites the paytxfee parameter.  
  
**Arguments:**  
1. amount \(numeric or string, required\) The transaction fee in NIX/kB  
  
**Result:**  
true\|false \(boolean\) Returns true if successful  
  
**Examples:**  
&gt; nix-cli settxfee 0.00001  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "settxfee", "params": \[0.00001\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  


`signmessage "address" "message"` Sign a message with the private key of an address. Requires wallet passphrase to be set with walletpassphrase call.  
  
**Arguments:**  
1. "address" \(string, required\) The nix address to use for the private key.  
2. "message" \(string, required\) The message to create a signature of.  
  
**Result:**  
"signature" \(string\) The signature of the message encoded in base 64  
  
**Examples:**  
Unlock the wallet for 30 seconds  
&gt; nix-cli walletpassphrase "mypassphrase" 30  
Create the signature  
&gt; nix-cli signmessage "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "my message"  
Verify the signature  
&gt; nix-cli verifymessage "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "signature" "my message"  
As json rpc  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "signmessage", "params": \["1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX", "my message"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  


`walletlock` Removes the wallet encryption key from memory, locking the wallet. After calling this method, you will need to call walletpassphrase again before being able to call any methods which require the wallet to be unlocked.  
  
**Examples:**  
Set the passphrase for 2 minutes to perform a transaction  
&gt; nix-cli walletpassphrase "my pass phrase" 120  
Perform a send \(requires passphrase set\)  
&gt; nix-cli sendtoaddress "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 1.0  
Clear the passphrase since we are done before 2 minutes is up  
&gt; nix-cli walletlock  
As json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "walletlock", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  


`walletpassphrase <passphrase> <timeout> [stakingonly]` Stores the wallet decryption key in memory for 'timeout' seconds. This is needed prior to performing transactions related to private keys such as sending NIX  
  
**Arguments:**  
1. "passphrase" \(string, required\) The wallet passphrase  
2. timeout \(numeric, required\) The time to keep the decryption key in seconds. Limited to at most 1073741824 \(2^30\) seconds. Any value greater than 1073741824 seconds will be set to 1073741824 seconds.  
3. stakingonly \(bool, optional\) If true, sending functions are disabled.  
  
Note: Issuing the walletpassphrase command while the wallet is already unlocked will set a new unlock time that overrides the old one. If \[stakingonly\] is true and &lt;timeout&gt; is 0, the wallet will remain unlocked for staking until manually locked again.  
  
**Examples:**  
Unlock the wallet for 60 seconds  
&gt; nix-cli walletpassphrase "my pass phrase" 60  
Lock the wallet again \(before 60 seconds\)  
&gt; nix-cli walletlock  
Unlock the wallet to stake  
&gt; nix-cli walletpassphrase "my pass phrase" 0 true  
As json rpc call  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "walletpassphrase", "params": \["my pass phrase", 60\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/  


`walletpassphrasechange "oldpassphrase" "newpassphrase"` Changes the wallet passphrase from 'oldpassphrase' to 'newpassphrase'.  
  
**Arguments:**  
1. "oldpassphrase" \(string\) The current passphrase  
2. "newpassphrase" \(string\) The new passphrase  
  
**Examples:**  
&gt; nix-cli walletpassphrasechange "old one" "new one"  
&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "walletpassphrasechange", "params": \["old one", "new one"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

