# Borrow Balance

A user who borrows assets from the protocol is subject to accumulated interest based on the current [borrow rate](borrow-rate.md). Interest is accumulated every block and integrations may use this function to obtain the current value of a user's borrow balance with interest.

**ABep20 / ABNB**

```text
function borrowBalanceCurrent(address account) returns (uint)
```

* `account`: The account which borrowed the assets.
* `RETURN`: The user's current borrow balance \(with interest\) in units of the underlying asset.

**Solidity**

```text
ABep20 aToken = AToken(0x3FDA...);
uint borrows = aToken.borrowBalanceCurrent(msg.caller);
```

**Web3 1.0**

```javascript
const aToken = ABNB.at(0x3FDB...);
const borrows = await aToken.methods.borrowBalanceCurrent(account).call();
```

