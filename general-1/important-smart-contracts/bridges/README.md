# Bridges



The bridge, based on POA's bridge implementation, is used to transfer Besc tokens between the Besc chain and the Ethereum network.

Tokens sent to the respective bridge contract on one network (whether it's Besc or Ethereum) are "locked" in the bridge, "unlocked" on the other network bridge and transferred to the sender.

The validators of the bridge on both network are the Besc chain validators. This means that validators, as part of their governance responsibilities, also need to validate bridge transactions and therefore hold Besc tokens to "approve" bridge transactions on Besc chain and hold ETH to "approve" transactions on Ethereum.

Each bridge transaction must be approved by a majority (over 50%) of the validators in order to be processed successfully.

The bridge contracts are deployed on both networks, and bridge oracle processes run on each validators machine as part of the validator deployment stack.

Besides the transfer of Besc tokens between the two networks, the bridge is also responsible for network core functionality events:

**Mint block reward distributed on the Besc chain on Ethereum**

Each cycle the total block reward distributed on Besc chain is minted on Ethereum and locked on the bridge contract.

This works by listening to the \`RewardedOnCycle\` event emitted by the BlockReward contract on Besc chain, waiting for all bridge validators on Besc chain to sign it, and eventually sending a transaction to mint on Ethereum (by the last signing validator).

**Update Besc chain validators on Ethereum**

Each cycle the Besc chain validators are selected from a random snapshot of pending validators.

Those validators, being also the bridge validators, need to be updated on bsc as well.

This works by listening to the \`InitiateChange\` event emitted by the Consensus contract on Besc chain, waiting for all bridge validators on Besc chain to sign it, and eventually sending a transaction to set the bridge validators on Ethereum (by the last signing validator).

[https://bridge.bescbridge.network/bridge](https://bridge.bescbridge.network/bridge)
