# Other Install Methods

It is also possible to manually set up your node. This is not recommended for the inexperience user as it will most likely lead to difficulties at some point should you mess up. Hence, the steps will only be briefly mentioned here:

1. Get your VPS ready with Ubuntu 16.04 / 18.04.
2. Install all dependencies for NIX \(listed below\).
3. Clone the [repository](https://github.com/NixPlatform/NixCore) at the latest tag.
4. Compile with **make CFLAGS=-fPIC**
5. Create and configure ~/.nix/nix.conf on the VPS.
6. Create and configure ghostnode.conf in your NIX installation directory.
7. Start the node from your wallet.

```text
apt-get install -y -o Dpkg::Options::="--force-confdef" -o Dpkg::Options::="--force-confold" make software-properties-common \
  build-essential libtool autoconf libssl-dev libboost-dev libboost-chrono-dev libboost-filesystem-dev libboost-program-options-dev \
  libboost-system-dev libboost-test-dev libboost-thread-dev sudo automake git wget curl libdb4.8-dev bsdmainutils libdb4.8++-dev \
  libminiupnpc-dev libgmp3-dev unzip libzmq3-dev ufw pkg-config libevent-dev libdb5.3++
```

