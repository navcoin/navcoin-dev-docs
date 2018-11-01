---
title: Configure NavCoin
linktitle: Configure NavCoin
description: How to configure NavCoin Core with a configuration file.
date: 2013-07-01
publishdate: 2017-01-02
lastmod: 2017-03-05
categories: [fundamentals]
keywords: [configuration]
weight: 60
sections_weight: 60
draft: false
toc: true
---

NavCoin uses a file called `navcoin.conf` to store it's configuration settings. This located in the `.navcoin4` appdata folder (see below for a more specific location)  and is user editable.

The user can choose to override the entire default configuration file by specifying an alternative, or overwrite individual configuration options by specifying them
using the command line at launch.

Examples:

```bash
navcoind -conf="~/Documents/altConfig.conf" # use an alternative config
navcoind -rpcport=33333 -rpcuser=alternativeuser -rpcpassword=example # override specific options
```

{{% note %}}
Alternate config files can be specified as a [launch option](/launch-options) using the `-conf=/path/to/file.conf` switch.
{{% /note %}}

## All Configuration Settings

A full list of options that can be specified in a config file can be found on the [launch options page](/launch-options), however the `-` is unneeded when specifying options in a config.  

```bash
-rpcuser=user # This is INCORRECT, the hyphen is not needed
rpcuser=user # This is CORRECT
```

Options that normally have no argument (e.g. `-testnet`, `-regtest`, etc) are activated by setting a `1` (enable) or `0` (disable) to enable or disable them.
```bash
staking=0
testnet=1
```

## Configuration Lookup Order

The configuation file is read top-to-bottom and any setting will be overwritten if there is another instance of the same setting below it.

```bash
rpcport=50000
rpcuser=user
rpcport=60000 # Overrides the rpcport setting above
```

## Example Configuration

The following is a typical example of a configuration file:

```bash
rpcuser=user
rpcpassword=mysecretpassword
testnet=1
rpcport=60000
printtoconsole=1
```

## Default configuration file location

By default the config file will not exist and you will need to create one but, the default location the wallet will look for the config file is in the NavCoin data folder.
You can specify an alternative datafolder or confuration file location when launching the wallet from the command line.

### Default locations

Windows: `C:\Users\(YOUR USERNAME)\AppData\Roaming\NavCoin4\`

Linux: `~/.navcoin4/`

MacOS: `~/Library/Application Support/NavCoin4/`

NavPi: `/home/stakebox/.navcoin4/`