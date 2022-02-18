# Get Current Votes

Gets the balance of votes for an account as of the current block.

**Atlantis**

```text
function getCurrentVotes(address account) returns (uint96)
```

* `account`: Address of the account in which to retrieve the number of votes.
* `RETURN`: The number of votes \(integer\).

**Solidity**

```text
Atlantis atl = Atlantis(0x123...); // contract address
uint votes = atl.getCurrentVotes(0xabc...);
```

**Web3 1.2.6**

```javascript
const account = '0x123...'; // contract address
const votes = await atl.methods.getCurrentVotes(account).call();
```

