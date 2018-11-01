---
title: Quick Start
linktitle: Quick Start
description: Learn how to interface with the blockchain by connecting to the NavCoin daemon and running RPC commands.
date: 2013-07-01
publishdate: 2013-07-01
categories: [getting started]
keywords: [quick start,usage]
authors: [Shekhar Gulati, Ryan Watters]
menu:
  docs:
    parent: "getting-started"
    weight: 10
weight: 10
sections_weight: 10
draft: false
aliases: [/quickstart/,/overview/quickstart/,/]
toc: true
---

{{% note %}}
This quick start uses `macOS` in the examples. For instructions about how to install NavCoin on other operating systems, see [install](/getting-started/installing).
{{% /note %}}


## Step 1: Install NavCoin

See this page on [installing](/getting-started/installing) NavCoin.
{{% note %}}
You will need `navcoind` (the navcoin daemon) and `navcoin-cli`, so you'll need to download one of the .tars or .zips of the wallet instead of an installer, as they contain these files and the installers don't.
{{% /note %}}

## Step 2: Choose your network

NavCoin has four blockchains that you can choose to sync with:

- Mainnet
- Testnet
- Devnet
- Regtest

Each of these networks has a different purpose, to read about what they are for and how they co-exist, see [navcoin-networks]

For this quick start guide we will assume you want to connect to the Testnet.

## Step 3: Connect to the Test Network and sync the blockchain

There are two ways to pass configuration options to the daemon, via arguments you pass when you launch the wallet daemon, or via a config file.
You can also do both at the same time, however anything passed via cli arguments will overwrite anything in the config file.

### Command line arguments

When launching from the command line, run `navcoind -testnet -rpcuser="user" -rpcpass="pass"` to launch the wallet in Testnet mode.

### Configuration file

The default location for the NavCoin config file is:  

```bash
~/Library/Application Support/NavCoin4/navcoin.conf # MacOS
C:\Users\(YOUR USERNAME)\AppData\Roaming\NavCoin4\navcoin.conf  # Windows
~/.navcoin4/navcoin.conf  # Linux
```  

If it doesn't exist, create it.  
Inside this file add the lines:

```bash
testnet=1
rpcuser="user"
rpcpassword="pass"
```

Now when you launch the wallet it will connect to the Testnet.

## Step 4: Run an RPC command from the console

Inside a terminal `cd` to where you extracted the NavCoin executables.  

```bash
cd ~/Downloads/navcoin-4.4.0/bin/
```

If you haven't launched it in Testmode already, run `navcoind -testnet -rpcuser="user" -rpcpass="pass"` to launch the wallet daemon.
Next (in a new terminal window) run:  
```bash
./navcoin-cli -testnet getinfo # The -testnet flag is needed as our wallet is connected to the testnet
```
You should get an output similar to this:  
```json
{
  "version": 4040000,
  "protocolversion": 70020,
  "walletversion": 130000,
  "balance": 0.00000000,
  "newmint": 0.00000000,
  "stake": 0.00000000,
  "blocks": 1199,
  "communityfund": {
    "available": 0.00000000,
    "locked": 0.00000000
  },
  "timeoffset": 0,
  "ntptimeoffset": 0,
  "connections": 1,
  "proxy": "",
  "testnet": true,
  "keypoololdest": 1539830083,
  "keypoolsize": 100,
  "paytxfee": 0.00100000,
  "relayfee": 0.00010000,
  "errors": ""
}
```
Congrats you've just run your first RPC command via the console!  
To get a list of RPC commands you can run, run the command `./navcoin-cli -testnet help`


## Step 5: Run an RPC command using Postman

- First install Postman from [here](https://www.getpostman.com/).  
- Open it up and also make sure you've launched your wallet in Testnet mode like in Step 4.
- In Postman configure these settings:
  - Set the request type to `POST`
  - Under the 'Body' tab 




[navcoin-networks]: /navcoin-networks/
