# ATokens

Each asset supported by the Atlantis protocol is integrated through a aToken contract, which is an [EIP-20](https://eips.ethereum.org/EIPS/eip-20) compliant representation of balances supplied to the protocol. By minting aTokens, users \(1\) earn interest through the aToken's exchange rate, which increases in value relative to the underlying asset, and \(2\) gain the ability to use aTokens as collateral.

aTokens are the primary means of interacting with the Atlantis protocol; when a user mints, redeems, borrows, repays a borrow, liquidates a borrow, or transfers aTokens, she will do so using the aToken contract.

There are currently two types of aTokens: ABep20 and ABNB. Though both types expose the EIP-20 interface, ABep20 wraps an underlying ERC-20 asset, while ABNB simply wraps Ether itself. As such, the core functions which involve transferring an asset into the protocol have slightly different interfaces depending on the type, each of which is shown below.

## How do aTokens earn interest?

Each market has its own Supply interest rate \(APR\). Interest isn't distributed; instead, simply by holding aTokens, you'll earn interest.

aTokens accumulates interest through their exchange rate — over time, each aToken becomes convertible into an increasing amount of it's underlying asset, even while the number of aTokens in your wallet stays the same.

## Can you walk me through an example?

Let’s say you supply 1,000 USDC to the Atlantis protocol, when the exchange rate is 0.020070; you would receive 49,825.61 sUSDC \(1,000/0.020070\).

A few months later, you decide it’s time to withdraw your USDC from the protocol; the exchange rate is now 0.021591:

* Your 49,825.61 sUSDC is now equal to 1,075.78 USDC \(49,825.61 \* 0.021591\)
* You could withdraw 1,075.78 USDC, which would redeem all 49,825.61 sUSDC
* Or, you could withdraw a portion, such as your original 1,000 USDC, which would redeem 46,315.59 sUSDC \(keeping 3,510.01 sUSDC in your wallet\)

## How do I view my aTokens?

Each aToken is visible on [BSCScan](https://bscscan.com), and you should be able to view them in the list of tokens associated with your address


## Can I transfer aTokens?
Yes, but exercise caution! By transferring aTokens, you’re transferring your balance of the underlying asset inside the Atlantis protocol. If you send a aToken to your friend, your balance \(viewable in the [Atlantis Interface](https://atlantis.loans/)\) will decline, and your friend will see their balance increase.

A aToken transfer will fail if the account has [entered](../comptroller/enter-markets.md) that aToken market and the transfer would have put the account into a state of negative [liquidity](../comptroller/get-account-liquidity.md).

