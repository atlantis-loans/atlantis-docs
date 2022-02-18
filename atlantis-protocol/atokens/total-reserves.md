# Total Reserves

Reserves are an accounting entry in each aToken contract that represents a portion of historical interest set aside as [cash](get-cash.md) which can be withdrawn or transferred through the protocol's governance. A small portion of borrower interest accrues into the protocol, determined by the [reserve factor](reserve-factor.md).

**ABep20 / ABNB**

```text
function totalReserves() returns (uint)
```

* `RETURN`: The total amount of reserves held in the market.

**Solidity**

```text
ABep20 aToken = AToken(0x3FDA...);
uint reserves = aToken.totalReserves();
```

**Web3 1.0**

```javascript
const aToken = ABNB.at(0x3FDB...);
const reserves = (await aToken.methods.totalReserves().call());
```

