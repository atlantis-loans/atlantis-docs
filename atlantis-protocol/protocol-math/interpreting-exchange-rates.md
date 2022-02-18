# Interpreting Exchange Rates

The aToken [Exchange Rate](../../atokens/exchange-rate.md) is scaled by the difference in decimals between the aToken and the underlying asset.

```javascript
const oneATokenInUnderlying = exchangeRateCurrent / (1 * 10 ^ (18 + underlyingDecimals - aTokenDecimals))
```

Here is an example of finding the value of 1 aUSDC in USDC with Web3.js JavaScript.

```javascript
const aTokenDecimals = 8; // all aTokens have 8 decimal places
const underlying = new web3.eth.Contract(bep20Abi, batAddress);
const aToken = new web3.eth.Contract(aTokenAbi, aUsdcAddress);
const underlyingDecimals = await underlying.methods.decimals().call();
const exchangeRateCurrent = await aToken.methods.exchangeRateCurrent().call();
const mantissa = 18 + parseInt(underlyingDecimals) - aTokenDecimals;
const oneATokenInUnderlying = exchangeRateCurrent / Math.pow(10, mantissa);
console.log('1 aUSDC can be redeemed for', oneATokenInUnderlying, 'USDC');
```

There is no underlying contract for ETH, so to do this with aETH, set `underlyingDecimals` to 18.

To find the number of underlying tokens that can be redeemed for aTokens, multiply the number of aTokens by the above value `oneATokenInUnderlying`.

```javascript
const underlyingTokens = aTokenAmount * oneATokenInUnderlying
```

