# Borrow Rate

At any point in time one may query the contract to get the current borrow rate per block.

**ABep20 / ABNB**

```text
function borrowRatePerBlock() returns (uint)
```

* `RETURN`: The current borrow rate as an unsigned integer, scaled by 1e18.

**Solidity**

```text
ABep20 aToken = AToken(0x3FDA...);
uint borrowRateMantissa = aToken.borrowRatePerBlock();
```

**Web3 1.0**

```javascript
const aToken = ABNB.at(0x3FDB...);
const borrowRate = (await aToken.methods.borrowRatePerBlock().call()) / 1e18;
```

