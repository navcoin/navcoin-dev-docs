

---
title: Block Height And Forking
linktitle: Block Height And Forking
description: Learn what is block height and blockchain forking
date: 2018-05-25
layout: single
keywords: ["GDPR", "Privacy", "Data Protection"]
menu:
  docs:
    parent: "about"
    weight: 10
weight: 10
sections_weight: 10
draft: false
aliases: [/privacy/,/gdpr/]
toc: true
---

Any NavCoin staker who successfully hashes a block header to a value below the target threshold can add the entire block to the block chain (assuming the block is otherwise valid). These blocks are commonly addressed by their block height—the number of blocks between them and the first Bitcoin block (block 0, most commonly known as the genesis block). For example, block 2016 is where difficulty could have first been adjusted.

![Transaction Propagation](/img/en-blockchain-fork.svg)

Multiple blocks can all have the same block height, as is common when two or more stakers each produce a block at roughly the same time. This creates an apparent fork in the block chain, as shown in the illustration above.

When miners produce simultaneous blocks at the end of the block chain, each node individually chooses which block to accept. In the absence of other considerations, discussed below, nodes usually use the first block they see.

Every 30 seconds a staker produces another block which attaches to only one of the competing simultaneously-mined blocks. This makes that side of the fork stronger than the other side. Assuming a fork only contains valid blocks, normal peers always follow the most difficult chain to recreate and throw away stale blocks belonging to shorter forks. (Stale blocks are also called orphans or orphan blocks, but those terms are also used for true orphan blocks without a known parent block.)

Long-term forks are possible if different stakers work at cross-purposes, such as some stakers diligently working to extend the block chain at the same time other miners are attempting a 51 percent attack to revise transaction history.

Since multiple blocks can have the same height during a block chain fork, block height should not be used as a globally unique identifier. Instead, blocks are usually referenced by the hash of their header (often with the byte order reversed, and in hexadecimal).