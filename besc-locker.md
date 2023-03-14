---
description: >-
  Liquidity locks are tools used to restrict the ability to withdraw or sell
  tokens from a liquidity pool.
---

# BESC Locker

They are often used to ensure that liquidity providers are committed to supporting a market and to prevent them from "rug-pulling" or manipulating prices.

Unvest's liquidity lock tool differs from conventional solutions in that it is completely free to use and has no fees for locking or redeeming tokens. You can create as many locks as you like, including partial locks and partial unlocks, and choose whether to unlock your tokens suddenly or gradually.

Locks for your token are displayed publicly on your Investor Dashboard, which can increase credibility and build trust with stakeholders.

{% hint style="info" %}
Once created, liquidity locks are permanent and cannot be undone, hidden, or deleted. They are also permissionless, meaning that you cannot withdraw or cancel your locks until the unlock date.
{% endhint %}

Unvest's liquidity lock tool uses a variant of the vestingTokens smart contract to create liquidLock tokens, which are ERC20 tokens that represent a claim for your LP token but are programmatically locked until the vesting date.

This means that you can trade liquidLocks, make them composable into other DeFi apps, and even sell them or use them as loan collateral. However, the holder cannot withdraw the liquidity until the vesting date.

We recommend using the liquidity lock tool on testnet first to get familiar with it before your launch date. This will help ensure that your launch goes as smoothly as possible.
