# How to Trade

Trading on PancakeSwap is very easy compared to most exchanges. You aren't going to be overwhelmed by charts or jargon, and calculations are all handled for you.

### Getting set up to trade

Before you can trade, you will need a BESC compatible wallet.  You will also need to have some BESC20 tokens to trade with.

### Trading on the BeanSwap exchange

1\. Go to the exchange page [here](https://beanswap.finance/swap).

2\. Unlock your BeanEco Smart Chain-compatible wallet by clicking **Unlock Wallet** (you can also **Connect** in the top right-hand corner). If you haven't yet connected your wallet BeanSwap.

![](<../../../../../.gitbook/assets/Screenshot (3) (2).png>)

3\. Choose the token you want to trade from the dropdown menu in the "From" section. The default setting is BESC.

![](<../../../../../.gitbook/assets/Screenshot (4).png>)

Whichever token you choose, you will need to make sure you have some to trade with. Your balance is shown above the token dropdown menu.

4\. Choose the token you want to trade to in the "To" section as above. Next, type an amount for your "To" currency by clicking inside the input box.

![](<../../../../../.gitbook/assets/Screenshot (4).png>)

Your "From" currency amount will be estimated automatically. You can also type your "From" amount and have the "To" amount estimate automatically if you like.

5\. Check the details, and click the **Swap** button.

![](<../../../../../.gitbook/assets/Screenshot (3) (2).png>)

6\. A window with more details will appear. Check the details are correct.

![](<../../../../../.gitbook/assets/Screenshot (4).png>)

When you are ready, click the **Confirm Swap** button. Your wallet will ask you to confirm the action.

7\. Done! You can click **View on BescScan** to see your transaction details on the explorer.

![](broken-reference)

## How come my transaction won't go through?

BeanSwap is a DeFi application such that it interacts with the wallet to complete on-chain transactions for swapping, creating LPs, staking in farms and pools, etc. &#x20;

### Gas Fees

As such, the first thing is to **make sure you have enough BESC to pay for the gas fee** of the on-chain transactions. Typically, gas fee fluctuates depending on the number of transactions in the queue, if there are more transactions, a higher gas fee may be required to push through the transaction.

### Transaction Fees

If your swapping action still doesn't go through and it is displaying an error for you to revise the slippage -- you may want to check if the tokens you are trying to swap has **any fees and restrictions on transactions**.

It is not uncommon for tokens on BNB Smart Chain to include a **transaction fee** in their contracts, usually these fees could be used for burning, funding a treasury of a fair launch project -- for example, this APX token has an 1% tax on every transaction for sending to a burn address, such that more transactions would mean more burning, accruing value to APX token holders.&#x20;

With the transaction fee, whether it is inclusive (a portion of the swap amount is sent elsewhere than your address so the output is less than expected for the estimated input) or exclusive (requiring an additional transfer from your address to send extra tokens so the input is more than expected for the estimated output), it affects the input and output amount that you agree for signing the transaction. In many cases, the transaction cannot meet the input and output requirements because of the tax.

### Swapping with Transaction Fees

Before you swap any tokens, make sure you have visited their website to understand if they have a transaction fee mechanism (or _tax_ as many projects put it). If there is, make sure you set a slippage that is sufficient to accommodate the transaction fee -- e.g. if there is a transaction fee of 5%, your slippage will have to be set at at least 5% plus the normal trading slippage depending on your trading amount and the token's liquidity, say 5.5%-6%.&#x20;

In some extreme cases including some scams, some tokens even have a block on most or all transfers on chain, or only allowing certain addresses to sell, in such case it is impossible to swap the token successfully. Do learn about the token you are trying to swap and be aware of any fees and restrictions!
