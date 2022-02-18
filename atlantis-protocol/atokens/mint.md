# Mint

The mint function transfers an asset into the protocol, which begins accumulating interest based on the current [Supply Rate](supply-rate.md) for the asset. The user receives a quantity of aTokens equal to the underlying tokens supplied, divided by the current [Exchange Rate](exchange-rate.md).

**ABep20**

```text
function mint(uint mintAmount) returns (uint)
```

* `msg.sender`: The account which shall supply the asset, and own the minted aTokens.
* `mintAmount`: The amount of the asset to be supplied, in units of the underlying asset.
* `RETURN`: 0 on success, otherwise an [Error code](error-codes.md)

Before supplying an asset, users must first [approve](https://eips.ethereum.org/EIPS/eip-20#approve) the aToken to access their token balance.

**ABNB**

```text
function mint() payable
```

* `msg.value` _\[payable\]_: The amount of ether to be supplied, in wei.
* `msg.sender`: The account which shall supply the ether, and own the minted aTokens.
* `RETURN`: No return, reverts on error.

**Solidity**

```text
Erc20 underlying = Erc20(0xToken...);     // get a handle for the underlying asset contract
ABep20 aToken = ABep20(0x3FDA...);        // get a handle for the corresponding aToken contract
underlying.approve(address(aToken), 100); // approve the transfer
assert(aToken.mint(100) == 0);            // mint the aTokens and assert there is no error
```

**Web3 1.0**

```javascript
const aToken = ABNB.at(0x3FDB...);
await aToken.methods.mint().send({from: myAccount, value: 50});
```

