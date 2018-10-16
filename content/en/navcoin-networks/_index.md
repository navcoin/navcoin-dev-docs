---
date: 2018-04-16
title: "NavCoin Networks"
slug: navcoin-networks
url: /navcoin-networks/
toc: true
sections_weight: 10

---

There are a number of networks you can connect to when launching the wallet.
By default you launch on the mainnet, all of the other networks are for various forms of testing.


### Chain selection options


```bash
-testnet

# Launches with the test chain. Functions the same as the mainnet.
# This is generally considered to be stable and is suitable for testing any kind of application or node on.

-devnet  

# Launches with the dev chain. Functions the same as the mainnet but with faster timings for block generation and community fund proposals.
# This is intended for developers to test changes with a network.

-regnet

# Launches with the regression chain.
# The regnet is generally intended for solo testing, however it is possible to connect multiple clients to one regnet (it won't connect to them by default though).
# It attempts to create a new genesis block on launch and the wallet will fail to launch is there is an existing `regnet` folder containing data in your wallet data directoty.
# The regnet allows you to manipulate the blockchain with console commands (e.g. you can generate blocks at will with the generate commands).
```