# Besc Consensus

Consensus is a fault-tolerant mechanism that is used in blockchain systems to achieve the necessary agreement on the single state of the network. Besc network is using a Delegated Proof of Stake DPoS consensus model. DPoS is a variation of Proof of Stake consensus. In PoS there are a set of validators that are responsible for keeping the network updated and validating the network's state. They do this in turns, every validator has their turn in line. On their turn the validator updates the network's state, and the rest of the validators check that the update is valid.

![](<../../.gitbook/assets/image (7).png>)

Consensus contract is used to manage the list of the network validators and delegators

BlockReward contract is calculates the reward amount that validators and delegators will receive on each block validation. The reward size is proportional to validator's stake.

With Voting contract validators are vote on various changes on these 3 base level contracts. All those contracts are proxied with implementation that handles the logic. The implementations can be changed only by the Voting process.

The bridge is used to transfer the Besc native token between Besc and Ethereum networks.

## [Consensus - 0xc6119816bB72c980d99861FeF89F6ceDe5D362A5](https://bescscan.io/address/0xc6119816bB72c980d99861FeF89F6ceDe5D362A5)

This contract is responsible for handling the network DPos consensus. The contract stores the current validator set and chooses a new validator set at the end of each cycle. The logic for updating the validator set is to select a random snapshot from the snapshots taken during the cycle.

The snapshots are taken of pending validators, who are those which staked more than the minimum stake needed to become a network validator. Therefore the contract is also responsible for staking, delegating and withdrawing those funds.

Stake amount for a validator is the sum of staked and delegated amount to it's address.

This contract is based on \`non-reporting ValidatorSets.

{% hint style="info" %}
minimum stake amount = 10,000 Besc token

cycle duration blocks = 34560 (approximately 2 days)
{% endhint %}

## [Block Reward - 0x8AE455f5e77F2fF26F8aD69cf8464AA12aaAeAd8](https://bescscan.io/address/0x8AE455f5e77F2fF26F8aD69cf8464AA12aaAeAd8)

This contract is responsible for generating and distributing block rewards to the network validators according to the network specs (2% yearly inflation).

Another role of this contract is to call the snapshot/cycle logic on the Consensus contract

This contract is based on \`BlockReward.

## [Voting - 0x59F8F812bdEd2eaCFDbD27D55c01FCfC2E349E8b](https://bescscan.io/address/0x59F8F812bdEd2eaCFDbD27D55c01FCfC2E349E8b)

This contract is responsible for opening new ballots and voting to accept/reject them. Ballots are basically offers to change other network contracts implementation.

Only network validators can open new ballots, everyone can vote on them, but only validators votes count when the ballot is closed.

Ballots are opened/closed on cycle end.

{% hint style="info" %}
max number of open ballots = 100

max number of open ballots per validator = 100 / number of validators

minimum ballot duration (cycles) = 2

maximum ballot duration (cycles) = 14
{% endhint %}

## [Proxy Storage](https://bescscan.io/address/0xA588aFF49C5b3a8fc97c2ab8F63c37586a4c99C6)

This contract is responsible for holding network contracts implementation addresses and upgrading them if necessary (via voting).
