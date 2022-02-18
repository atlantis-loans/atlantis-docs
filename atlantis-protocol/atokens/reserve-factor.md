# Reserve Factor

The reserve factor defines the portion of borrower interest that is converted into [reserves](total-reserves.md).

**ABep20 / ABNB**

```text
function reserveFactorMantissa() returns (uint)
```

* `RETURN`: The current reserve factor as an unsigned integer, scaled by 1e18.

**Solidity**

```text
ABep20 aToken = AToken(0x3FDA...);
uint reserveFactorMantissa = aToken.reserveFactorMantissa();
```

**Web3 1.0**

```javascript
const aToken = ABNB.at(0x3FDB...);
const reserveFactor = (await aToken.methods.reserveFactorMantissa().call()) / 1e18;
```

