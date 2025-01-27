---
description: >-
  Margin trade with global DEX liquidity! No perps or synthetics, only PURE real
  spot assets.
---

# Margin Trading: PURE

{% hint style="info" %}
Underneath, the protocol logic and contracts are the same! Different dApps simply help different user bases get to their desired positions quicker.
{% endhint %}

<figure><img src="../.gitbook/assets/gearbox pure margin trading (1).png" alt=""><figcaption><p><a href="https://pure.gearbox.fi/">https://pure.gearbox.fi/</a></p></figcaption></figure>

The PURE margin trading interface helps you enter leverage positions quickly, without having to go through a complex Credit Account opening process. Here you can find:

1. **Flexible Leverage:** You can either select how much of an asset you want to long - and then change your initial capital amount OR leverage factor. Or choose how much initial capital you want to go into a position with - and then chance your leverage factor.
2. **Position Management:** Check your liquidation price, leverage factor, borrow rate, slippage, and so on. You can also change these parameters later, after a position is open. The only thing that is staying in tact is your debt asset. That stays the same until you close that Credit Account.
3. **Visualized Charts:** The chart will draw a line for you to show you the liquidation price. Once you adjust your collateral (add more or increase your debt instead), the line will move accordingly.

## Why is it PURE? What's cool here?

<figure><img src="../.gitbook/assets/gearbox pure margin trading.png" alt=""><figcaption><p>Click the green button at the top right corner: <a href="https://pure.gearbox.fi/">https://pure.gearbox.fi/</a></p></figcaption></figure>

The name PURE is not an abbreviation. It literally means _pure_ leverage. The reason why it's pure is because Gearbox leverage isn't about perpetuals or isolated liquidity. With Gearbox:

* **Real assets:** you trade with real spot assets, no perps or synthetics.
* **Deep liquidity:** you trade with global DEX liquidity of Uniswap, Curve, Balancer, and other DEXes. Your trades literally happen on those DEXes, not inside Gearbox pools.
* **No funding rates:** you have no funding rates, only borrow rates which are often cheaper.
* **No price wicks:** you have no price wicks like on BitMex, because oracles are not inwards-looking. In case the third-party oracles (ChainLink, Redstone) malfunction though, that is still a possibility.
* **Gearbots UX:** you can create any kind of limit orders and stop losses yourself, managing your trades fully onchain. You can do so without trusting any server, because those are fully onchain.
* **Farm with your leveraged position:** you can utilise your leverage positions in farming and constructing interesting strategies if you want to do so, for example, you can read more about that on the [Leverage 2.0 page](../what-can-you-do-with-leverage-2.0.md). We call them boosted long/shorts.

<figure><img src="../.gitbook/assets/gearbox infinite dex liquidity.png" alt=""><figcaption><p><a href="https://pure.gearbox.fi/trade">pure.gearbox.fi</a></p></figcaption></figure>

## Trading Strategies Ideas

In terms of what you can do with margin trading, the following strategies are possible:&#x20;

* **Long margin trading: t**raders borrow funds to buy an asset with the expectation that its price will rise. The aim is to sell the asset at a higher price to repay the borrowed funds and keep the profit.&#x20;
* **Short margin trading:** borrowing an asset to sell it with the expectation that its price will fall. Traders aim to buy back the asset at a lower price, repay the borrowed funds, and keep the profit. Since shorting depends on the assets you borrow, you can only short BTC, ETH and stables currently. Ability to short more assets will increase as their lending pools are created.
* **Boosted Longs/Shorts:** Gearbox is composable, you can go ahead and deploy your leveraged position on other protocols. This enables users to earn APYs on their leveraged positions by directly leverage trading assets like sDAI, yWETH, yDAI and yUSDC. [Read about Boosted Trades](strategies/long.md).
* **Pairs trading:** simultaneously entering both long and short positions in two correlated assets. Traders aim to profit from the relative performance of the two assets. An example of this would be instantaneous leverage on the BTC/ETH pair, just borrow ETH on leverage and swap it to BTC. Same can be done to create other BTC and ETH relative pairs. More [here](https://www.investopedia.com/terms/p/pairstrade.asp).
* **Basis trading:** profiting from borrow rate differences of the same asset on different markets or exchanges while remaining delta neutral is a common strategy. You can long an asset on Gearbox for a borrow fee that’s lower than most funding fee and short the same asset elsewhere to earn funding fee. This enables you to stay delta neutral and still earn through the rate arbitrage

{% hint style="success" %}
If you would want to get more out of margin trading, you can later click on "Extended dApp" in the interface and configure your position further. For example, make your short or long - farm at the same time. Many of these [leverage 2.0 actions](../what-can-you-do-with-leverage-2.0.md) are possible, just dive in!
{% endhint %}
