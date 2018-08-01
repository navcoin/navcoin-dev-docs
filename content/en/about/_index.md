---
title: Blockchain
linktitle: Blockchain
description: Hugo's features, roadmap, license, and motivation.
date: 2017-02-01
publishdate: 2017-02-01
lastmod: 2017-02-01
categories: []
keywords: []
menu:
  docs:
    parent: "about"
    weight: 1
weight: 1
draft: false
aliases: [/about-hugo/,/docs/]
toc: false
---

The block chain provides Bitcoin’s public ledger, an ordered and timestamped record of transactions. This system is used to protect against double spending and modification of previous transaction records.

Each full node in the Bitcoin network independently stores a block chain containing only blocks validated by that node. When several nodes all have the same blocks in their block chain, they are considered to be in consensus. The validation rules these nodes follow to maintain consensus are called consensus rules. This section describes many of the consensus rules used by Bitcoin Core.