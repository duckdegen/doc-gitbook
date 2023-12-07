---
description: 'Passive lending on Gearbox Protocol: supply & earn APY.'
---

# Pools & APY



{% hint style="success" %}
Non-custodial. No impermanent loss. Isolated. Multiple earn streams. No liquidations.
{% endhint %}

* Earning with Gearbox is as simple as lending on Compound or Aave. Next to that, pools are semi-isolated. Lend liquidity in the asset you choose and start earning APY! No impermanent loss.
* With Gearbox's Credit Account model, your assets never end up in custody of any one person or company. They are held on an isolated smart contract after they are borrowed.&#x20;

![](<../../.gitbook/assets/Screenshot 2021-08-07 at 22.49.25.png>)

The asset you lend to the protocol would be able to be utilized, aka borrowed for leverage, by traders & farmers who would be actively rebalancing their positions or using some other strategies within the [AllowedList](../../overview/credit-account/#allowed-list-policy) which a [Credit Account](../../overview/credit-account/) allows. As borrowers, they will be required by the protocol to pay different fees which accrue to the underlying pools of those assets, the staked dTokens. See below.

The positions which traders and farmers take should be liquidated by third-party [liquidators](../../overview/liquidations/) before the assets of liquidity providers would start being exposed to the downside. As such, the protocol returns the liquidity providers’ assets to the pools. This is how Gearbox is able to provide composable leverage.

{% hint style="info" %}
Because Gearbox architecture is modular, there can exist multiple pools for the same asset. Each pool would then be isolated from one another and can have different [AllowedList](../../overview/credit-account/allowedlist-policy/).

**Gearbox lending pools are ERC-4626.**
{% endhint %}

## Pool tokens: (staked) Diesel Tokens

When you supply capital to a pool, you get Diesel Tokens, also known as dTokens, back. These tokens automatically earn interest & fees proportional to your share of the pool [like cTokens on Compound](https://compound.finance/docs/ctokens) or Yearn LP tokens. You don’t need to claim interest or perform any other actions, your Diesel Tokens grow in value. _This is if the pool doesn't suffer losses from incorrect liquidations._

Getting Diesel tokens is super easy, you can try it out by [supplying liquidity to Gearbox Protocol](../manage-liquidity.md#supplying-liquidity).

{% content-ref url="../manage-liquidity.md" %}
[manage-liquidity.md](../manage-liquidity.md)
{% endcontent-ref %}

{% hint style="success" %}
As for the GEAR or any other extra token yields, those are accruing to your **staked** dTokens too, but you need to claim them. _How often?_ - That's up to you to decide. Simply click on the rewards tab in the top right corner of the interface or do it onchain yourself.
{% endhint %}

## Where does the yield come from?

The yield comes from multiple sources:

1. Borrowers pay fees according to the regular utilization curve (explained below). The more the liquidity in the pools is utilized, the higher the rate. This is similar to other lending protocols.
2. Borrowers pay extra fees according to the quota fees (see in [Protocol Fees](../../overview/protocol-fees.md)). These fees can be configured by GEAR stakers and vary from epoch to epoch. See the [Gauges page](../../governance/quotas-and-gauges.md) for more.
3. Any extra rewards in the form of GEAR or other tokens that are being available.

### 1. Two-Tick Utilization Curve

Capital is required for traders and farmers to get leverage for their financial operations. For this, there are Liquidity Pools: anyone can become a liquidity provider by supplying assets in the Liquidity Pool. The profitability of LPs depends on the pool utilization ratio _U_ - the higher utilization, the higher interest rate. Borrow APY is calculated according to formula:

$$
r(t) = 
    \begin{cases}
        r_0 + \frac{U(t)}{U_1}\left(r_1-r_0\right), & U(t) \le U_1\\
        r_1 + \left(U(t)-U_2\right)\frac{r_2-r_1}{U_2-U_1}, & U(t) \in (U_1,U_2].\\
        r_2 + \left(U(t)-U_2\right)\frac{r_3-r_2}{1-U_2}, & U(t) > U_2.\\
    \end{cases}
$$

Previously, when a new Credit Account was opened or closed to utilization 1-tick, the rates would skyrocket or drop instantly. That is because the state of the curve was either cheap to borrow or insanely expensive to borrow. That made decision-making for both users confusing. With the new model which is two-tick, it introduces three states essentially: cheap to borrow, high but acceptable rate for borrowing, and insanely expensive to borrow.

<table><thead><tr><th width="211">Asset pool</th><th width="86">r_0</th><th width="80">r_1</th><th width="87">r_2</th><th width="79" data-type="number">r_3</th><th width="83">U_1</th><th>U_2</th></tr></thead><tbody><tr><td>USDC</td><td>0</td><td>1</td><td>1.25</td><td>100</td><td>70</td><td>90</td></tr><tr><td>ETH</td><td>0</td><td>2</td><td>2.5</td><td>60</td><td>70</td><td>90</td></tr><tr><td>WBTC</td><td>0</td><td>2</td><td>2.5</td><td>60</td><td>70</td><td>90</td></tr></tbody></table>

### 2. Quota Fees

The above was the only source of organic yield previously. With V3, there are also Quota fees. Those quota fees are shared between passive lender pools (thus making APYs higher) as well as the DAO. If you are trying to calculate the passive lending organic APY, take quota fees into account,

{% content-ref url="../../overview/protocol-fees.md" %}
[protocol-fees.md](../../overview/protocol-fees.md)
{% endcontent-ref %}

***

{% hint style="info" %}
There are also things like max borrow limit, pool limits - for different Credit Managers. Check the [AllowedList Policy](../../overview/credit-account/allowedlist-policy/) page for the links to understand this better. Alternatively, the interface shows this information as well, in a minimalistic way. [See the explanation](../manage-liquidity.md).
{% endhint %}