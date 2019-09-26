# Initial Setup

## Required Files

#### nixd

You'll need a running instance of nixd which can be downloaded from [https://github.com/NixPlatform/NixCore/releases](https://github.com/NixPlatform/NixCore/releases). After you've downloaded the nixd binary, create a config file in `~/.nix` named `nix.conf` and configure the daemon to your liking. A working and valid example is shown below. Once configured, simply execute nixd or setup a systemd service to manage it.

#### SDK

You can use yarn or npm to install the SDK.

```text
yarn add nix-core
```

or

```text
npm install nix-core --save
```

## Node Configuration

To establish a connection between the nixd instance and the SDK, an appropriate nix.conf configuration file is required. This is a working example:

{% code-tabs %}
{% code-tabs-item title="nixd.conf" %}
```text
daemon=1
server=1
par=1
rpcbind=127.0.0.1
rpcallowip=127.0.0.1
rpcport=3335
rpcuser=username1
rpcpassword=password1
rpcclienttimeout=30
rpcthreads=2
rpcworkqueue=1000
staking=0
enableaccounts=1
```
{% endcode-tabs-item %}
{% endcode-tabs %}

### Connecting to the daemon in JavaScript

After nixd has been started with the above configuration, an instance can be created in the controlling JavaScript file:

```text
    const Client = require('nix-core');
    const client = new Client({
        username: 'username1',
        password: 'password1',
        port: 3335,
        network: 'mainnet' });
```

More options can be found in the nix-core package documentation. With the `client` object, any command can now be executed. A list of selected commands can be found [here](usage-guide.md).

