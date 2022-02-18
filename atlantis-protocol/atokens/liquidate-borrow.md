# Liquidate Borrow

A user who has negative account liquidity is subject to liquidation by other users of the protocol to return his/her account liquidity back to positive \(i.e. above the collateral requirement\). When a liquidation occurs, a liquidator may repay some or all of an outstanding borrow on behalf of a borrower and in return receive a discounted amount of collateral held by the borrower; this discount is defined as the liquidation incentive.

A liquidator may close up to a certain fixed percentage \(i.e. close factor\) of any individual outstanding borrow of the underwater account. Unlike in v1, liquidators must interact with each aToken contract in which they wish to repay a borrow and seize another asset as collateral. When collateral is seized, the liquidator is transferred aTokens, which they may redeem the same as if they had supplied the asset themselves. Users must approve each aToken contract before calling liquidate \(i.e. on the borrowed asset which they are repaying\), as they are transferring funds into the contract.

**ABep20**

```text
function liquidateBorrow(address borrower, uint amount, address collateral) returns (uint)
```

* `msg.sender`: The account which shall liquidate the borrower by repaying their debt and seizing their collateral.
* `borrower`: The account with negative [account liquidity](../comptroller/get-account-liquidity.md) that shall be liquidated.
* `repayAmount`: The amount of the borrowed asset to be repaid and converted into collateral, specified in units of the underlying borrowed asset.
* `aTokenCollateral`: The address of the aToken currently held as collateral by a borrower, that the liquidator shall seize.
* `RETURN`: 0 on success, otherwise an [Error code](error-codes.md)

Before supplying an asset, users must first [approve](https://eips.ethereum.org/EIPS/eip-20#approve) the aToken to access their token balance.

**ABNB**

```text
function liquidateBorrow(address borrower, address aTokenCollateral) payable
```

* `msg.value` _\[payable\]_: The amount of ether to be repaid and converted into collateral, in wei.
* `msg.sender`: The account which shall liquidate the borrower by repaying their debt and seizing their collateral.
* `borrower`: The account with negative [account liquidity](../comptroller/get-account-liquidity.md) that shall be liquidated.
* `aTokenCollateral`: The address of the aToken currently held as collateral by a borrower, that the liquidator shall seize.
* `RETURN`: No return, reverts on error.

**Solidity**

```text
ABNB aToken = ABNB(0x3FDB...);
ABep20 aTokenCollateral = ABep20(0x3FDA...);
require(aToken.liquidateBorrow.value(100)(0xBorrower, aTokenCollateral) == 0, "borrower underwater??");
```

**Web3 1.0**

```javascript
const aToken = ABep20.at(0x3FDA...);
const aTokenCollateral = ABNB.at(0x3FDB...);
await aToken.methods.liquidateBorrow(0xBorrower, 33, aTokenCollateral).send({from: 0xLiquidator});
```

