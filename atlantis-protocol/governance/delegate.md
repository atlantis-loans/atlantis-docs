# Delegate

Delegate votes from the sender to the delegatee. Users can delegate to 1 address at a time, and the number of votes added to the delegatee’s vote count is equivalent to the balance of Atlantis in the user’s account. Votes are delegated from the current block and onward, until the sender delegates again, or transfers their Atlantis.

**Atlantis**

```text
function delegate(address delegatee)
```

* `delegatee`: The address in which the sender wishes to delegate their votes to.
* `msg.sender`: The address of the Atlantis token holder that is attempting to delegate their votes.
* `RETURN`: No return, reverts on error.

**Solidity**

```text
Atlantis atl = Atlantis(0x123...); // contract address
atl.delegate(delegateeAddress);
```

**Web3 1.2.6**

```javascript
const tx = await atl.methods.delegate(delegateeAddress).send({ from: sender });
```

