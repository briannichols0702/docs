# Bridges



The bridge, based on POA's bridge implementation, is used to transfer BESC tokens between the BESC chain and the Ethereum network.

Tokens sent to the respective bridge contract on one network (whether it's BESC or BSC) are "locked" in the bridge, "unlocked" on the other network bridge and transferred to the sender.

The validators of the bridge on both networks are the BESC validators. This means that validators, as part of their governance responsibilities, also need to validate bridge transactions and therefore hold BESC tokens to "approve" bridge transactions on BESC chain and hold BNB to "approve" transactions on BSC.

Each bridge transaction must be approved by a majority (over 50%) of the validators in order to be processed successfully.

The bridge contracts are deployed on both networks, and bridge oracle processes run on each validators machine as part of the validator deployment stack.

Besides the transfer of BESC tokens between the two networks, the bridge is also responsible for network core functionality events:

**Mint block reward distributed on the BESC Chain on BSC**

Each cycle the total block reward distributed on BESC chain is minted on BSC and locked on the bridge contract.

This works by listening to the \`RewardedOnCycle\` event emitted by the BlockReward contract on BESC chain, waiting for all bridge validators on BESC chain to sign it, and eventually sending a transaction to mint on BSC (by the last signing validator).

**Update BESC chain validators on BSC**

Each cycle the BESC chain validators are selected from a random snapshot of pending validators.

Those validators, being also the bridge validators, need to be updated on BSC as well.

This works by listening to the \`InitiateChange\` event emitted by the Consensus contract on BESC chain, waiting for all bridge validators on BESC chain to sign it, and eventually sending a transaction to set the bridge validators on BSC (by the last signing validator).

Bridge contracts

{% embed url="https://bescscan.io/address/0xc6EcAb2E8Dc0b7612fb2B122EafD88bB83C63677" %}

{% embed url="https://www.bscscan.com/address/0x5ce292abc7956027d710c4402d2e8b3d4ae1d315" %}

{% embed url="https://bscscan.com/address/0xD99eB86D9BbaA908f1160e4dd02838cBa374360A" %}

{% embed url="https://bescscan.io/address/0x8b9Ff934e7880d6F071261c32E6e5c893f70B802" %}

{% embed url="https://bescscan.io/address/0xd32d6dA15a7a9d42d6CC84A200FFe0B07cf5bf4f" %}

{% embed url="https://bescscan.io/address/0x6cA4680fbDD5c29cc0174Ae9d6a822f09Ba1BF76" %}

{% embed url="https://bridge.bescbridge.network/bridge" %}
