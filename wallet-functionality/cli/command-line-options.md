# Command Line Options

Command line options can be used when starting your NIX core wallet or in the nix.conf configuration file. Startup options will override nix.conf entries.

**Usage:**  
nix-qt \[command-line options\]  
nixd \[command-line options\]

**Example:**

```bash
nixd -bind=123.123.123.123
```

**or add to the nix.conf file as:**  
\[option \(without -\)\]=\[value\]

**Example:**

```text
bind=123.123.123.123
```

## Options

`-?` Print this help message and exit

`-version` Print version and exit

`-alertnotify=<cmd>` Execute command when a relevant alert is received or we see a really long fork \(%s in cmd is replaced by message\)

`-blocknotify=<cmd>` Execute command when the best block changes \(%s in cmd is replaced by block hash\)

`-assumevalid=<hex>` If this block is in the chain assume that it and its ancestors are valid and potentially skip their script verification \(0 to verify all, default: 0000000000000000000000000000000000000000000000000000000000000000, testnet: 0000000000000000000000000000000000000000000000000000000000000000\)

`-conf=<file>` Specify configuration file \(default: nix.conf\)

`-datadir=<dir>` Specify data directory

`-dbcache=<n>` Set database cache size in megabytes \(4 to 16384, default: 450\)

`-loadblock=<file>` Imports blocks from external blk000??.dat file on startup

`-debuglogfile=<file>` Specify location of debug log file: this can be an absolute path or a path relative to the data directory \(default: debug.log\)

`-maxorphantx=<n>` Keep at most &lt;n&gt; unconnectable transactions in memory \(default: 100\)

`-maxmempool=<n>` Keep the transaction memory pool below &lt;n&gt; megabytes \(default: 300\)

`-mempoolexpiry=<n>` Do not keep transactions in the mempool longer than &lt;n&gt; hours \(default: 336\)

`-persistmempool` Whether to save the mempool on shutdown and load on restart \(default: 1\)

`-blockreconstructionextratxn=<n>` Extra transactions to keep in memory for compact block reconstructions \(default: 100\)

`-par=<n>` Set the number of script verification threads \(-4 to 16, 0 = auto, &lt;0 = leave that many cores free, default: 0\)

`-pid=<file>` Specify pid file \(default: nixd.pid\)

`-prune=<n>` Reduce storage requirements by enabling pruning \(deleting\) of old blocks. This allows the pruneblockchain RPC to be called to delete specific blocks, and enables automatic pruning of old blocks if a target size in MiB is provided. This mode is incompatible with -txindex and -rescan. Warning: Reverting this setting requires re-downloading the entire blockchain. \(default: 0 = disable pruning blocks, 1 = allow manual pruning via RPC, &gt;550 = automatically prune block files to stay under the specified target size in MiB\)

`-reindex-chainstate` Rebuild chain state from the currently indexed blocks

`-reindex` Rebuild chain state and block index from the blk\*.dat files on disk

`-sysperms` Create new files with system default permissions, instead of umask 077 \(only effective with disabled wallet functionality\)

`-txindex` Maintain a full transaction index, used by the getrawtransaction rpc call \(default: 1\)

`-addressindex` Maintain a full address index, used to query for the balance, txids and unspent outputs for addresses \(default: 0\)

`-timestampindex` Maintain a timestamp index for block hashes, used to query blocks hashes by a range of timestamps \(default: 0\)

`-spentindex` Maintain a full spent index, used to query the spending txid and input index for an outpoint \(default: 0\)

## Connection options

`-addnode=<ip>` Add a node to connect to and attempt to keep the connection open \(see the 'addnode' RPC command help for more info\)

`-banscore=<n>` Threshold for disconnecting misbehaving peers \(default: 100\)

`-bantime=<n>` Number of seconds to keep misbehaving peers from reconnecting \(default: 86400\)

`-bind=<addr>` Bind to given address and always listen on it. Use \[host\]:port notation for IPv6

`-connect=<ip>` Connect only to the specified node\(s\); -connect=0 disables automatic connections \(the rules for this peer are the same as for -addnode\)

`-discover` Discover own IP addresses \(default: 1 when listening and no -externalip or -proxy\)

`-dns` Allow DNS lookups for -addnode, -seednode and -connect \(default: 1\)

`-dnsseed` Query for peer addresses via DNS lookup, if low on addresses \(default: 1 unless -connect used\)

`-externalip=<ip>` Specify your own public address

`-forcednsseed` Always query for peer addresses via DNS lookup \(default: 0\)

`-listen` Accept connections from outside \(default: 1 if no -proxy or -connect\)

`-listenonion` Automatically create Tor hidden service \(default: 1\)

`-maxconnections=<n>` Maintain at most &lt;n&gt; connections to peers \(default: 125\)

`-maxreceivebuffer=<n>` Maximum per-connection receive buffer, &lt;n&gt;\*1000 bytes \(default: 5000\)

`-maxsendbuffer=<n>` Maximum per-connection send buffer, &lt;n&gt;\*1000 bytes \(default: 1000\)

`-maxtimeadjustment` Maximum allowed median peer time offset adjustment. Local perspective of time may be influenced by peers forward or backward by this amount. \(default: 4200 seconds\)

`-onion=<ip:port>` Use separate SOCKS5 proxy to reach peers via Tor hidden services \(default: -proxy\)

`-onlynet=<net>` Only connect to nodes in network &lt;net&gt; \(ipv4, ipv6 or onion\)

`-permitbaremultisig` Relay non-P2SH multisig \(default: 1\)

`-peerbloomfilters` Support filtering of blocks and transaction with bloom filters \(default: 1\)

`-port=<port>` Listen for connections on &lt;port&gt; \(default: 6214 or testnet: 16214\)

`-proxy=<ip:port>` Connect through SOCKS5 proxy

`-proxyrandomize` Randomize credentials for every proxy connection. This enables Tor stream isolation \(default: 1\)

`-seednode=<ip>` Connect to a node to retrieve peer addresses, and disconnect

`-timeout=<n>` Specify connection timeout in milliseconds \(minimum: 1, default: 5000\)

`-torcontrol=<ip>:<port>` Tor control port to use if onion listening enabled \(default: 127.0.0.1:9051\)

`-torpassword=<pass>` Tor control port password \(default: empty\)

`-upnp` Use UPnP to map the listening port \(default: 0\)

`-whitebind=<addr>` Bind to given address and whitelist peers connecting to it. Use \[host\]:port notation for IPv6

`-whitelist=<IP address or network>` Whitelist peers connecting from the given IP address \(e.g. 1.2.3.4\) or CIDR notated network \(e.g. 1.2.3.0/24\). Can be specified multiple times. Whitelisted peers cannot be DoS banned and their transactions are always relayed, even if they are already in the mempool, useful e.g. for a gateway

`-maxuploadtarget=<n>` Tries to keep outbound traffic under the given target \(in MiB per 24h\), 0 = no limit \(default: 0\)

## Wallet options

`-addresstype` What type of addresses to use \("legacy", "p2sh-segwit", or "bech32", default: "p2sh-segwit"\)

`-changetype` What type of change to use \("legacy", "p2sh-segwit", or "bech32"\). Default is same as -addresstype, except when -addresstype=p2sh-segwit a native segwit output is used when sending to a native segwit address\)

`-disablewallet` Do not load the wallet and disable wallet RPC calls

`-keypool=<n>` Set key pool size to &lt;n&gt; \(default: 1000\)

`-fallbackfee=<amt>` A fee rate \(in NIX/kB\) that will be used when fee estimation has insufficient data \(default: 0.0002\)

`-discardfee=<amt>` The fee rate \(in NIX/kB\) that indicates your tolerance for discarding change by adding it to the fee \(default: 0.0001\). Note: An output is discarded if it is dust at this rate, but we will always discard up to the dust relay fee and a discard fee above that is limited by the fee estimate for the longest target

`-mintxfee=<amt>` Fees \(in NIX/kB\) smaller than this are considered zero fee for transaction creation \(default: 0.00001\)

`-paytxfee=<amt>` Fee \(in NIX/kB\) to add to transactions you send \(default: 0.00\)

`-rescan` Rescan the block chain for missing wallet transactions on startup

`-salvagewallet` Attempt to recover private keys from a corrupt wallet on startup

`-spendzeroconfchange` Spend unconfirmed change when sending transactions \(default: 1\)

`-txconfirmtarget=<n>` If paytxfee is not set, include enough fee so transactions begin confirmation on average within n blocks \(default: 6\)

`-walletrbf` Send transactions with full-RBF opt-in enabled \(RPC only, default: 0\)

`-upgradewallet` Upgrade wallet to latest format on startup

`-wallet=<file>` Specify wallet file \(within data directory\) \(default: wallet.dat\)

`-walletbroadcast` Make the wallet broadcast transactions \(default: 1\)

`-walletdir=<dir>` Specify directory to hold wallets \(default: &lt;datadir&gt;/wallets if it exists, otherwise &lt;datadir&gt;\)

`-walletnotify=<cmd>` Execute command when a wallet transaction changes \(%s in cmd is replaced by TxID\)

`-zapwallettxes=<mode>` Delete all wallet transactions and only recover those parts of the blockchain through -rescan on startup \(1 = keep tx meta data e.g. account owner and payment request information, 2 = drop tx meta data\)

## Wallet staking options

`-staking` Stake your coins to support network and gain reward \(default: true\)

`-stakingthreads` Number of threads to start for staking, max 1 per active wallet, will divide wallets evenly between threads \(default: 1\)

`-minstakeinterval=<n>` Minimum time in seconds between successful stakes \(default: 0\)

`-minersleep=<n>` Milliseconds between stake attempts. Lowering this param will not result in more stakes. \(default: 500\)

`-reservebalance=<amount>` Ensure available balance remains above reservebalance. \(default: 0\)

`-donationpercent=<n>` Percentage of block reward donated to the donation address. e.g. 1190 \(11.90%\) \(default: 0\)

`-donationaddress=<n>` Destination to send donated staking rewards. \(default: N/A\)

`-stakesplitthreshold=<n>` Maximum amount of coins to stake before splitting into two outputs. \(default: 10000\)

`-stakecombinethreshold=<n>` Minimum amount of NIX to combine into one stake if wallet has multiple outputs to stake. \(default: 5000\)

`-maxstakecombine=<n>` Maximim of outputs to combine when achieving stakecombinethreshold. \(default: 3\)

`-generatenewstakingaddress` Create new bech32 addresses on successful stakes. \(default: false\)

`-minimumleasepercentage=<n>` Minimum lease percentage required for a contract to stake if you are leasing stakes. Value can be between 0 and 10000 e.g. 1191 \(11.91%\) \(default: 0\)

`-leaserewardaddresses=<n>` Stake only LPoS contracts with reward fee addresses specified by this command. e.g. x1,x2,x3 \(default: ""\)

`-leaserewardtome=<n>` Stake only LPoS contracts with reward fee addresses that this local wallet owns &lt;true/false&gt; \(default: false\)

`-dxmode` Set wallet change and default addressing to legacy for third-party dx support \(default: false\)

## ZeroMQ notification options

`-zmqpubhashblock=<address>` Enable publish hash block in &lt;address&gt;

`-zmqpubhashtx=<address>` Enable publish hash transaction in &lt;address&gt;

`-zmqpubrawblock=<address>` Enable publish raw block in &lt;address&gt;

`-zmqpubrawtx=<address>` Enable publish raw transaction in &lt;address&gt;

## Debugging/Testing options

`-uacomment=<cmt>` Append comment to the user agent string

`-debug=<category>` Output debugging information \(default: 0, supplying &lt;category&gt; is optional\). If &lt;category&gt; is not supplied or if &lt;category&gt; = 1, output all debugging information. &lt;category&gt; can be: net, tor, mempool, http, bench, zmq, db, rpc, estimatefee, addrman, selectcoins, reindex, cmpctblock, rand, prune, proxy, mempoolrej, libevent, coindb, qt, leveldb.

`-debugexclude=<category>` Exclude debugging information for a category. Can be used in conjunction with -debug=1 to output debug logs for all categories except one or more specified categories.

`-help-debug` Show all debugging options \(usage: --help -help-debug\)

`-logips` Include IP addresses in debug output \(default: 0\)

`-logtimestamps` Prepend debug output with timestamp \(default: 1\)

`-maxtxfee=<amt>` Maximum total fees \(in NIX\) to use in a single wallet transaction or raw transaction; setting this too low may abort large transactions \(default: 0.10\)

`-printtoconsole` Send trace/debug info to console instead of debug.log file

`-shrinkdebugfile` Shrink debug.log file on client startup \(default: 1 when no -debug\)

## Chain selection options

`-testnet` Use the test chain

## Node relay options

`-bytespersigop` Equivalent bytes per sigop in transactions for relay and mining \(default: 20\)

`-datacarrier` Relay and mine data carrier transactions \(default: 1\)

`-datacarriersize` Maximum size of data in data carrier transactions we relay and mine \(default: 83\)

`-mempoolreplacement` Enable transaction replacement in the memory pool \(default: 1\)

`-minrelaytxfee=<amt>` Fees \(in NIX/kB\) smaller than this are considered zero fee for relaying, mining and transaction creation \(default: 0.00001\)

`-whitelistrelay` Accept relayed transactions received from whitelisted peers even when not relaying transactions \(default: 1\)

`-whitelistforcerelay` Force relay of transactions from whitelisted peers even if they violate local relay policy \(default: 1\)

## Block creation options

`-blockmaxweight=<n>` Set maximum BIP141 block weight \(default: 3996000\)

`-blockmaxsize=<n>` Set maximum BIP141 block weight to this \* 4. Deprecated, use blockmaxweight

`-blockmintxfee=<amt>` Set lowest fee rate \(in NIX/kB\) for transactions to be included in block creation. \(default: 0.00001\)

## RPC server options

`-server` Accept command line and JSON-RPC commands

`-rest` Accept public REST requests \(default: 0\)

`-rpcbind=<addr>[:port]` Bind to given address to listen for JSON-RPC connections. This option is ignored unless -rpcallowip is also passed. Port is optional and overrides -rpcport. Use \[host\]:port notation for IPv6. This option can be specified multiple times \(default: 127.0.0.1 and ::1 i.e., localhost, or if -rpcallowip has been specified, 0.0.0.0 and :: i.e., all addresses\)

`-rpccookiefile=<loc>` Location of the auth cookie \(default: data dir\)

`-rpcuser=<user>` Username for JSON-RPC connections

`-rpcpassword=<pw>` Password for JSON-RPC connections

`-rpcauth=<userpw>` Username and hashed password for JSON-RPC connections. The field &lt;userpw&gt; comes in the format: &lt;USERNAME&gt;:&lt;SALT&gt;$&lt;HASH&gt;. A canonical python script is included in share/rpcuser. The client then connects normally using the rpcuser=&lt;USERNAME&gt;/rpcpassword=&lt;PASSWORD&gt; pair of arguments. This option can be specified multiple times

`-rpcport=<port>` Listen for JSON-RPC connections on &lt;port&gt; \(default: 6215 or testnet: 16215\)

`-rpcallowip=<ip>` Allow JSON-RPC connections from specified source. Valid for &lt;ip&gt; are a single IP \(e.g. 1.2.3.4\), a network/netmask \(e.g. 1.2.3.4/255.255.255.0\) or a network/CIDR \(e.g. 1.2.3.4/24\). This option can be specified multiple times

`-rpcserialversion` Sets the serialization of raw transaction or block hex returned in non-verbose mode, non-segwit\(0\) or segwit\(1\) \(default: 1\)

`-rpcthreads=<n>` Set the number of threads to service RPC calls \(default: 4\)

## UI options

`-choosedatadir` Choose data directory on startup \(default: 0\)

`-lang=<lang>` Set language, for example "de\_DE" \(default: system locale\)

`-min` Start minimized

`-rootcertificates=<file>` Set SSL root certificates for payment request \(default: -system-\)

`-splash` Show splash screen on startup \(default: 1\)

`-resetguisettings` Reset all settings changed in the GUI
