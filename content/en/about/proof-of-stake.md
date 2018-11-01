

---
title: Proof of Stake
linktitle: Proof of Stake
description: NavCoins Proof of Stake
date: 2018-05-25
layout: single
keywords: ["GDPR", "Privacy", "Data Protection"]
menu:
  docs:
    parent: "about"
    weight: 5
weight: 5
sections_weight: 5
draft: true
aliases: [/privacy/,/gdpr/]
toc: true
---
The block chain is collaboratively maintained by anonymous peers on the network, so Navcoin requires that each block is written by Navcoin holders (stakers) ensure that untrustworthy peers who want to modify past blocks have to work harder and hold more than NavCoin honest peers who only want to add and get rewarded by adding new blocks to the block chain.

Chaining blocks together makes it impossible to modify transactions included in any block without modifying all subsequent blocks. As a result, the amount of coins a user must hold to modify a particular block dramatically increases with every new block added to the block chain, magnifying the effect of Proof of Stake.

The proof of stake used in NavCoin takes advantage of the apparently random nature of cryptographic hashes. A good cryptographic hash algorithm converts arbitrary data into a seemingly-random number. If the data is modified in any way and the hash re-run, a new seemingly-random number is produced, so there is no way to modify the data to make the hash number predictable.

To prove you did some extra work to create a block, you must create a hash of the block header which does not exceed a certain value. For example, if the maximum possible hash value is 2256 − 1, you can prove that you tried up to two combinations by producing a hash value less than 2255.

In the example given above, you will produce a successful hash on average every other try. You can even estimate the probability that a given hash attempt will generate a number below the target threshold. NavCoin assumes a linear probability that the lower it makes the target threshold, the more hash attempts (on average) will need to be tried.

New blocks will only be added to the block chain if their hash is at least as challenging as a difficulty value expected by the consensus protocol. Every 2,016 blocks, the network uses timestamps stored in each block header to calculate the number of seconds elapsed between generation of the first and last of those last 2,016 blocks. The ideal value is 1,209,600 seconds (two weeks).

If it took fewer than two weeks to generate the 2,016 blocks, the expected difficulty value is increased proportionally (by as much as 300%) so that the next 2,016 blocks should take exactly two weeks to generate if hashes are checked at the same rate.

If it took more than two weeks to generate the blocks, the expected difficulty value is decreased proportionally (by as much as 75%) for the same reason.

(Note: an off-by-one error in the Bitcoin Core implementation causes the difficulty to be updated every 2,016 blocks using timestamps from only 2,015 blocks, creating a slight skew.)

Because each block header must hash to a value below the target threshold, and because each block is linked to the block that preceded it, it requires (on average) as much hashing power to propagate a modified block as the entire Bitcoin network expended between the time the original block was created and the present time. Only if you acquired a majority of the network’s hashing power could you reliably execute such a 51 percent attack against transaction history.

The block header provides several easy-to-modify fields, such as a dedicated nonce field, so obtaining new hashes doesn’t require waiting for new transactions. Also, only the 80-byte block header is hashed for proof-of-work, so including a large volume of transaction data in a block does not slow down hashing with extra I/O, and adding additional transaction data only requires the recalculation of the ancestor hashes in the merkle tree.