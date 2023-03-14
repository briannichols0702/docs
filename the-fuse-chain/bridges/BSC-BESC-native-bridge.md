---
description: >-
  Besc native bridge is used to relay the Besc native token between Besc and
  BSC network
---

# Besc: BSC ↔ Besc

Besc native bridge between Bsc and Besc is used to relay the Besc native token from Besc to Ethereum network

## Architecture Overview

The Besc bridged is based on POA's bridge implementation, it is used to transfer Besc tokens between the Besc chain and the Bsc network.

Tokens sent to the respective bridge contract on one network \(whether it's Besc or Bsc\) are "locked" in the bridge, "unlocked" on the other network bridge and transferred to the sender. The bridge contracts are deployed on both networks, and bridge oracle processes run on each validators machine as part of the validator deployment stack.

Besides the transfer of Besc tokens between the two networks, the bridge is also responsible for network core functionality events of relaying the block rewards to the Ethereum network:

**Mint block reward distributed on the Besc chain on Ethereum**

Each cycle the total block reward distributed on Besc chain is minted on bsc and locked on the bridge contract.

This works by listening to the \`RewardedOnCycle\` event emitted by the BlockReward contract on Besc chain, waiting for all bridge validators on Besc chain to sign it, and eventually sending a transaction to mint on Ethereum \(by the last signing validator\).

## Contracts

Home side of the bridge on the Besc network: [0xd32d6dA15a7a9d42d6CC84A200FFe0B07cf5bf4f]
(https://bescscan.io/address/0xd32d6dA15a7a9d42d6CC84A200FFe0B07cf5bf4f)
Foreign side of the bridge on the Ethereum network: [0xbe864aa7e4f802b7f7a3be2dc388b9d96e3f434c]
(https://bscscan.com/address/0xbe864aa7e4f802b7f7a3be2dc388b9d96e3f434c)

Besc token on the bsc network: [0x5e3344216adb2c19caa7f3fe90078e7c4ac71bb6](https://bscscan.com/token/0x5e3344216adb2c19caa7f3fe90078e7c4ac71bb6)

## Source Code

{% embed url="https://github.com/fuseio/fuse-bridge/tree/master/native-to-erc20/contracts" %}

## How to use

On Besc you send native Besc token to the home bridge contract. Then you receive an equal amount of the Besc token on the bsc network, sent from the foreign bridge contract

On bsc network you transfer the Besc token to the foreign bridge contract. After a couple of confirmations, you will receive equal amount of the Besc native token, sent from the home bridge contract.

#### 

