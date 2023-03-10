---
description: >-
  BNB inverse-native bridge is used to relay the BNB native token between
  Binance Smart Chain (BSC) and Besc networks
---

# BNB: BSC ↔ Besc

## Architecture Overview <a id="architecture-overview"></a>

This bridge is two layer bridge. In the base level the Arbitrary Message Bridge \(AMB\) is responsible for relaying messages between the networks. On top of the AMB, the pluggable mediators implement a contract logic of token relaying of various assets. More info [https://docs.tokenbridge.net/amb-bridge/about-amb-bridge](https://docs.tokenbridge.net/amb-bridge/about-amb-bridge)​‌

The contract is called an "inverse-native" bridge, because the home and foreign network are inversed. In that case Besc network is foreign and BSC is the home network.‌


## How to use <a id="how-to-use"></a>

To send token from the BSC network:‌

Send native BNB token to the home bridge contract. Then you receive an equal amount of the BNB token on the Besc network, sent from the foreign bridge contract.‌

To send token from the Besc network:‌

1. Approve the "BNB on Besc" TL20 token to be spent by the Foreign bridge.
2. Call relayTokens function on the bridge contract

the `relayTokens` method will lock the TL20 tokens on the foreign bridge. After a couple of confirmations, an equal amount of the BNB native token will be released from the home bridge contract on BSC.

#### ​ <a id="undefined"></a>

[  
](https://app.gitbook.com/@fuse-1/s/fuse-dev-docs/~/drafts/-MdkekktVnuRGEokLu71/bridges/bridges/eth-fuse-erc20-bridge/@merged)

