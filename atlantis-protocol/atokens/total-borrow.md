# Total Borrow

Total Borrows is the amount of underlying currently loaned out by the market, and the amount upon which interest is accumulated to suppliers of the market.

**ABep20 / ABNB**

```text
function totalBorrowsCurrent() returns (uint)
```

* `RETURN`: The total amount of borrowed underlying, with interest.

**Solidity**

```text
ABep20 aToken = AToken(0x3FDA...);
uint borrows = aToken.totalBorrowsCurrent();
```

**Web3 1.0**

```javascript
const aToken = ABNB.at(0x3FDB...);
const borrows = (await aToken.methods.totalBorrowsCurrent().call());
```

