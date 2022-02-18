# Borrowing

## Borrowing

Users are able to take a collateralized loan against their supplied assets in Atlantis. Once these assets are supplied, you can borrow based on the collateral factor of the asset. Typically collateral factors are set anywhere from 40% to 80%. For example, if Bitcoin has a collateral factor of 80%, that means you can borrow up to 80% of the value of your BTC.

## Collateral

Collateralized loans are given to a borrower in exchange of his crypto assets as collateral. Which translate to if you choice to set your asset as collateral you will be given a borrow credits.

> Note that if you set your asset as collateral and borrow other assets you can get liquidated. Example: Liquidation price of BNB is currently $247.71

## How-to borrow

After you supplied your assets and put them as collateral you are now eligible to borrow assets.

Borrowing function can be found under the **Lending** tab of the protocol. Clicking on any assets supported under the lending tab grants access to the borrowing function.

Below a image as this person is about to borrow $LINK. The Borrow APY indicates the current interest rate of borrowing $LINK. The Distribution APY indicates the incentive reward rates given by the Atlantis Protocol in Atlantis (ATL) token.

> If you borrowed assets on the Atlantis Protocol they are automatically set as collateral.

## Possibilities with borrow assets

It's your asset so you can do anything you want with it. I'll give you a few examples why people borrow assets.

* Leveraged Yield Farming - Staking the asset a Atlantis Protocol or other protocols (for example CAKE token at Pancakeswap)
* Recieve more daily atlantis rewards
* Leveraged Long position hodl'r (Long positions are where an investor gains exposure to cryptocurrency with the expectation that prices will rise at a later date, meaning that the asset can be sold for a profit. It is the opposite of a short position.)

## Repayments

Similar to Borrowing, Repayment function can be found under the **Lending** tab of the Protocol.

## Health

Health is a numeric representation of the degree of safety of user assets deposited as collateral. A higher value indicates that the user's funds have greater safety from liquidation. If Health goes below 1, a portion of the user's collateral can be liquidated. The Health of a user's funds is a dynamic state, and depends on the liquidation limit of the collateralized position against the value of the loan.

### Health fluctuations

Health is how “safe” your loan is, defined as the proportion of total deposited collateral against the total value of the loan. It increases or decreases based on the value fluctuation of the user's deposited asset value against the user's borrowed value.

> **Higher** Health value **improves** the user's collateral safety and borrow position **Lower** Health value **worsens** the user's collateral safety and borrow position

Having Health below 1 results in the potential liquidation of a portion of the user's collateral.

### Improving Health

To improve Health, the user can:

* Partail or full repayment of the collateralized loan
* Adding collaterals under "Supply"
