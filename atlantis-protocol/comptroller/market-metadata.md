# Market Metadata

The Comptroller contract has an array called `allMarkets` that contains the addresses of each aToken contract. Each address in the `allMarkets` array can be used to fetch a metadata struct in the Comptroller’s markets constant. See the [Comptroller Storage contract](https://github.com/atlantis-loans/atlantis-protocol-bsc/blob/main/contracts/ComptrollerStorage.sol) for the Market struct definition.

**Comptroller**

```text
AToken[] public allMarkets;
```

**Solidity**

```text
Comptroller troll = Comptroller(0xABCD...);
AToken aTokens[] = troll.allMarkets();
```

**Web3 1.2.6**

```javascript
const comptroller = new web3.eth.Contract(comptrollerAbi, comptrollerAddress);
const aTokens = await comptroller.methods.allMarkets().call();
const aToken = aTokens[0]; // address of a aToken
```

