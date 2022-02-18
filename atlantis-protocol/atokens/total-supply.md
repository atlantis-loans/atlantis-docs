# Total Supply

Total Supply is the number of tokens currently in circulation in this aToken market. It is part of the EIP-20 interface of the aToken contract.

**ABep20 / ABNB**

```text
function totalSupply() returns (uint)
```

* `RETURN`: The total number of tokens in circulation for the market.

**Solidity**

```text
ABep20 aToken = AToken(0x3FDA...);
uint tokens = aToken.totalSupply();
```

**Web3 1.0**

```javascript
const aToken = ABNB.at(0x3FDB...);
const tokens = (await aToken.methods.totalSupply().call());
```

