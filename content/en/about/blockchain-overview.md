

---
title: Blockchain Overview
linktitle: Overview
description: Understand the basics of a blockchain
date: 2018-05-25
layout: single
keywords: ["GDPR", "Privacy", "Data Protection"]
menu:
  docs:
    parent: "about"
    weight: 4
weight: 4
sections_weight: 4
draft: false
aliases: [/privacy/,/gdpr/]
toc: true
---

![Example image](/img/en-blockchain-overview.svg)

The illustration above shows a simplified version of a block chain. A block of one or more new transactions is collected into the transaction data part of a block. Copies of each transaction are hashed, and the hashes are then paired, hashed, paired again, and hashed again until a single hash remains, the merkle root of a merkle tree.

The merkle root is stored in the block header. Each block also stores the hash of the previous block’s header, chaining the blocks together. This ensures a transaction cannot be modified without modifying the block that records it and all following blocks.

Transactions are also chained together. Bitcoin wallet software gives the impression that satoshis are sent from and to wallets, but bitcoins really move from transaction to transaction. Each transaction spends the satoshis previously received in one or more earlier transactions, so the input of one transaction is the output of a previous transaction.


![Transaction Propagation](/img/en-blockchain-overview.svg)

A single transaction can create multiple outputs, as would be the case when sending to multiple addresses, but each output of a particular transaction can only be used as an input once in the block chain. Any subsequent reference is a forbidden double spend—an attempt to spend the same satoshis twice.

Outputs are tied to transaction identifiers (TXIDs), which are the hashes of signed transactions.

Because each output of a particular transaction can only be spent once, the outputs of all transactions included in the block chain can be categorized as either Unspent Transaction Outputs (UTXOs) or spent transaction outputs. For a payment to be valid, it must only use UTXOs as inputs.

Ignoring coinbase transactions (described later), if the value of a transaction’s outputs exceed its inputs, the transaction will be rejected—but if the inputs exceed the value of the outputs, any difference in value may be claimed as a transaction fee by the Bitcoin miner who creates the block containing that transaction. For example, in the illustration above, each transaction spends 10,000 satoshis fewer than it receives from its combined inputs, effectively paying a 10,000 satoshi transaction fee.