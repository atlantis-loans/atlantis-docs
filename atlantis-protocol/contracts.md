# Contracts

#### Atlantis Smart Contract Addresses

BSC: [0x1fD991fb6c3102873ba68a4e6e6a87B3a5c10271](https://bscscan.com/token/0x1fd991fb6c3102873ba68a4e6e6a87b3a5c10271)

Polygon: [0x0b68782eff3177f1f9240b64a7e2f8e0497e2454](https://polygonscan.com/token/0x0b68782eff3177f1f9240b64a7e2f8e0497e2454)

Avalanche: [0x90fBE9dfe76F6EF971c7A297641dfa397099a13e](https://snowtrace.io/token/0x90fbe9dfe76f6ef971c7a297641dfa397099a13e)



#### Smart Contract Source Codes

BSC: [https://github.com/atlantis-loans/atlantis-protocol-bsc/tree/main/contracts](https://github.com/atlantis-loans/atlantis-protocol-bsc/tree/main/contracts)

Polygon: [https://github.com/atlantis-loans/atlantis-protocol-polygon/tree/main/contracts](https://github.com/atlantis-loans/atlantis-protocol-polygon/tree/main/contracts)

Avalanche: [https://github.com/atlantis-loans/atlantis-protocol-avalanche](https://github.com/atlantis-loans/atlantis-protocol-avalanche)



**AToken, ABep20 and ABNB** \
****The Atlantis aTokens, which are self-contained borrowing and lending contracts. AToken contains the core logic and ABep20 and ABNB add public interfaces for Bep20 tokens and ether, respectively. Each AToken is assigned an interest rate and risk model (see InterestRateModel and Comptroller sections), and allows accounts to _mint_ (supply capital), _redeem_ (withdraw capital), _borrow_ and _repay a borrow_. Each AToken is an BEP-20 compliant token where balances represent ownership of the market.

**Comptroller**\
****The risk model contract, which validates permissible user actions and disallows actions if they do not fit certain risk parameters. For instance, the Comptroller enforces that each borrowing user must maintain a sufficient collateral balance across all aTokens.

**Atlantis**\
****The Atlantis Governance Token (ATL). Holders of this token have the ability to govern the protocol via the governor contract.

**Governor Alpha**\
****The administrator of the Atlantis timelock contract. Holders of Atlantis token may create and vote on proposals which will be queued into the Atlantis timelock and then have effects on Atlantis aToken and Comptroller contracts. This contract may be replaced in the future with a beta version.

**InterestRateModel**\
****Contracts which define interest rate models. These models algorithmically determine interest rates based on the current utilization of a given market (that is, how much of the supplied assets are liquid versus borrowed).\
\
**Careful Math**\
****Library for safe math operations.

**ErrorReporter**\
Library for tracking error codes and failure conditions.

**Exponential**\
Library for handling fixed-point decimal numbers.

**SafeToken**\
Library for safely handling Bep20 interaction.

**WhitePaperInterestRateModel**\
Initial interest rate model, as defined in the Whitepaper. This contract accepts a base rate and slope parameter in its constructor.
