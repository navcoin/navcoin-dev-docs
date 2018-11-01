---
date: 2018-04-16
title: "NavCoin Networks"
slug: navcoin-networks
url: /navcoin-networks/
toc: true
sections_weight: 10
weight: 60
sections_weight: 60
---

{{% note %}}
By default you launch on the mainnet, to connect to another network you must specify either via launch arguments or via the configuration file.
{{% /note %}}

There are a number of networks you can connect to when launching the wallet. All of the networks apart from the Mainnet are for various forms of testing.


## Networks

### Mainnet

The default network that wallets connect to. Uses the port 44444 for RPC calls.


### Testnet

Functions the same as the mainnet. Uses the port 44445 for RPC calls.  
This is generally considered to be stable and is suitable for testing any kind of application or node on.  

## Devnet  

Functions the same as the mainnet but with faster timings for block generation and community fund proposals. Uses the port 44446 for RPC calls.  
This is intended for developers to test changes with a network.

## Regnet

The Regnet is generally intended for solo testing, however it is possible to connect multiple clients to one regnet (it won't connect to them by default though). Uses the port 44446 for RPC calls.  
  
It attempts to create a new genesis block on launch and the wallet will fail to launch is there is an existing `regnet` folder inside your wallet data directory containing data in your wallet data directoty. The regnet allows you to manipulate the blockchain with console commands (e.g. you can generate blocks at will with the generate commands).

### Selecting a network

{{% note %}}
Command line arguments will override configuration files. If you specify multiple networks the last one specified will be the one used. 
{{% /note %}}


## Commandline launch arguments

Add these commands to your launch options to connect to the specified network.  
e.g. `navcoin-qt -testnet`

```bash
-testnet
# Launches with the test chain.

-devnet  
# Launches with the dev chain.

-regtest
# Launches with the regression chain.
```

## Configuration file options

Add these options to your configuration file to connect to the specified network

```bash
testnet=1
# Launches with the test chain.

devnet=1
# Launches with the dev chain.

regnet=1
# Launches with the regression chain.

```
