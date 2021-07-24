# BoardRoom

1. HONOR holders can stake HONOR in boardroom to earn ZENY inflation rewards.
2. Stake ZENY-USDC LP in FarmHero Yield Farm to earn HONOR.

## Launch Schedule

FarmHero Polygon will launch Boardroom, holder can stake HONOR to the Boardroom to get ZENY Inflation Reward.

ZENY is set to rebase according to its 12-hour time weighted average price every 12 hours.

In order to protect the benefit of HONOR holders, as well as protect front-running bots to buy most ZENY at liquidity-adding time. The team decide to distribute 1000 ZENY in first 36 hours via a ZENY Pool. 

Stake HONOR in ZENY pool to earn ZENY!

| DateTime | Item |
| :--- | :--- |
| 2021-07-13 14:00 UTC | Add 1000 Zeny-USDC LP to QuickSwap |
| 2021-07-13 14:00 UTC | Launch a 36-hour ZENY Pool \(1000 ZENY reward\) |
| 2021-07-13 14:30 UTC | Launch ZENY-USDC LP farm |
| 2021-07-16 14:00 UTC | 1st Rebase |

After that, regular Daily Rebase time: 02:00 and 14:00 UTC time.

## Rebase: Elastic Supply

1. There will be 2 pools in boardroom, X3 and X7 pool. 

   A. X3 pool can be freely entered or exited, it shares 30% of all inflation rewards.

   B. X7 pool funds will be locked for 49 hours on each inflation. 

   C. **Rewards can be claimed anytime. If ever a deflation happens, unclaimed rewards will be zero-out. Be sure to claim in time.**

2. Rebase will adjust the circulation supply of ZENY to the 12-hour time weighted average price \(12-hour TWAP\).  
3. Rebase time: 02:00 and 14:00 UTC time, daily.
4. Oracle: QuickSwap Oracle at the moment. Will add multiple oracle later to increase stability. 
5. On each rebase, 10% of inflation amount will be sent to Seigniorage contract. The contract will sell the ZENY into USDC at inflation and will used to buy back ZENY in times of price drop.

On 02:00 UTC and 14:00 UTC daily, the $ZENY inflation rewards will be sent to the pools for distribution over the whole epoch time \(12 hours\).

## Rebase: The Formula

If 12-hour ZENY TWAP &lt; 0.99, a burn will be triggered. The burn is global. It affects all contracts && wallets who owns ZENY.  In this case, total supply && circulation supply of ZENY will decrease.

```
Burn Amount = (1 - 12-hour ZENY TWAP) * total-zeny-supply
```

If 12-hour ZENY TWAP &gt; 1.01, an inflation will be triggered. The inflation reward comes from initial supply. No extra ZENY will be minted. In this case, total supply of zeny will not be changed, circulation supply will increase. 

Similar to AMPL, a buffer parameter is introduced when an inflation is triggered, this buffer parameter for now is 5. The buffer parameter help stabilise the ZENY price.

```text
Inflation Reward = (12-hour ZENY TWAP - 1) * circulation-supply / buffer
```

```
X3 POOL Reward = 0.3 * (Inflation Reward - Seigniorage)
```

```text
X7 POOL Reward = 0.7 * (Inflation Reward - Seigniorage)
```

```text
Seigniorage = Inflation Reward * 0.1
```

For more info, refer to:

{% page-ref page="../protocol/tokens/zeny.md" %}



