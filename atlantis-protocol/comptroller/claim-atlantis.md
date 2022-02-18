# Claim Atlantis

```
Atlantis = ATL or ATLX
```

Every Atlantis user accrues ATL for each block they are supplying to or borrowing from the protocol. Users may call the Comptroller's `claimAtlantis` method at any time to transfer Atlantis accrued to their address.

**Comptroller**

```text
// Claim all the Atlantis accrued by holder in all markets
function claimAtlantis(address holder) public

// Claim all the Atlantis accrued by holder in specific markets
function claimAtlantis(address holder, AToken[] memory aTokens) public

// Claim all the Atlantis accrued by specific holders in specific markets for their supplies and/or borrows
function claimAtlantis(address[] memory holders, AToken[] memory aTokens, bool borrowers, bool suppliers) public
```

**Solidity**

```text
Comptroller troll = Comptroller(0xABCD...);
troll.claimAtlantis(0x1234...);
```

**Web3 1.2.6**

```javascript
const comptroller = new web3.eth.Contract(comptrollerAbi, comptrollerAddress);
await comptroller.methods.claimAtlantis("0x1234...").send({ from: sender });
```

