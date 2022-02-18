# Exit Market

Exit a market - it is not an error to exit a market which is not currently entered. Exited markets will not count towards account liquidity calculations.

**Comptroller**

```text
function exitMarket(address aToken) returns (uint)
```

* `msg.sender`: The account which shall exit the given market.
* `aTokens`: The addresses of the aToken market to exit.
* `RETURN`: 0 on success, otherwise an [Error code](error-codes.md).

**Solidity**

```text
Comptroller troll = Comptroller(0xABCD...);
uint error = troll.exitMarket(AToken(0x3FDA...));
```

**Web3 1.0**

```javascript
const troll = Comptroller.at(0xABCD...);
const errors = await troll.methods.exitMarket(ABNB.at(0x3FDB...)).send({from: ...});
```

