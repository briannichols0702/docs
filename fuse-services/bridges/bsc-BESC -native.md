---
description: >-
  Besc native bridge is used to relay the Besc native token between Besc and
  Binance Smart Chain (BSC) networks
---

# Besc Native: BSC ↔ Besc

## Architecture Overview

This bridge is two layer bridge. In the base level the Arbitrary Message Bridge \(AMB\) is responsible for relaying messages between the networks. On top of the AMB,  the pluggable mediators implement a contract logic of token relaying of various assets. More info [https://docs.tokenbridge.net/amb-bridge/about-amb-bridge](https://docs.tokenbridge.net/amb-bridge/about-amb-bridge)

## Contracts

Home side of the bridge on the Besc network: [0xf9b276A1A05934ccD953861E8E59c6Bc428c8cbD](https://bescscan.io/address/0xf9b276A1A05934ccD953861E8E59c6Bc428c8cbD/transactions)a3Fe39c9040e7e3E9caA7F0D5bd6)

## Source Code

[https://github.com/fuseio/tokenbridge-contracts](https://github.com/fuseio/tokenbridge-contracts)

## How to use

To send token from the Besc network:

Send native Besc token to the home bridge contract. Then you receive an equal amount of the Besc token on the BSC network, sent from the foreign bridge contract.

To send token from the BSC network:

1. Approve the Besc TL20 tokens to be spent by the Foreign TL20 bridge. 
2. Call relayTokens function on the bridge contract

the `relayTokens` method will lock the TL20 tokens on the foreign bridge. After a couple of confirmations, an equal amount of the Besc TL20 token will be released from the home bridge contract on BSC.

#### 

#### 

