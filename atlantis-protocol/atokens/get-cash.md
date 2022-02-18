# Get Cash

Cash is the amount of underlying balance owned by this aToken contract. One may query the total amount of cash currently available to this market.

**ABep20 / ABNB**

```text
function getCash() returns (uint)
```

* `RETURN`: The quantity of underlying asset owned by the contract.

**Solidity**

```text
ABep20 aToken = AToken(0x3FDA...);
uint cash = aToken.getCash();
```

**Web3 1.0**

```javascript
const aToken = ABNB.at(0x3FDB...);
const cash = (await aToken.methods.getCash().call());
```

