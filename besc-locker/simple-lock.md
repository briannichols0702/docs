---
description: >-
  A simple liquidity lock is a lock that has one sudden unlock date, where 100%
  of the LP tokens unlock.
---

# Simple Lock

{% hint style="info" %}
This type of lock is useful for projects that want to ensure that their liquidity remains locked for a certain amount of time, but do not want to create a more complex vesting schedule.
{% endhint %}

To create a simple liquidity lock, you will need to select the LP address that you want to lock, and choose which token in the LP pair is the project token. This will allow the lock to be linked to the Investor dashboard. You will also need to specify the length of the lock, as well as the name and symbol for the lock.

Name the lock and supply a symbol, this will be used to name the liquidLock token that wraps your LP token. It is important to pick a name and symbol thoughtfully, as they cannot be changed later and will be publicly visible on the Investor Dashboard.

Liquidity locks are permanent and cannot be undone, hidden, or deleted. They are also permissionless, meaning that LPs cannot withdraw or cancel the lock until the unlock date. For these reasons, it is recommended to use the liquidity lock tool on the testnet first to get familiar with it before your launch date. This will help ensure that your launch day goes as smoothly as possible.\
