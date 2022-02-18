# Exchange Rate

Each aToken is convertible into an ever increasing quantity of the underlying asset, as interest accrues in the market. The exchange rate between a aToken and the underlying asset is equal to:

```text
exchangeRate = (getCash() + totalBorrows() - totalReserves()) / totalSupply()
```

**ABep20 / ABNB**

```text
function exchangeRateCurrent() returns (uint)
```

* `RETURN`: The current exchange rate as an unsigned integer, scaled by 1e18.

**Solidity**

```text
ABep20 aToken = AToken(0x3FDA...);
uint exchangeRateMantissa = aToken.exchangeRateCurrent();
```

**Web3 1.0**

```javascript
const aToken = ABNB.at(0x3FDB...);
const exchangeRate = (await aToken.methods.exchangeRateCurrent().call()) / 1e18;
```

Tip: note the use of call vs. send to invoke the function from off-chain without incurring gas costs.

