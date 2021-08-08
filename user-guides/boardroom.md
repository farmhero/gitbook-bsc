---
description: THE ALGO STABLECOIN
---

# BoardRoom

## Earn

1. HERO holders can stake HERO in boardroom to earn ZENNY inflation rewards.
2. Stake ZENNY-BUSD LP in FarmHero Yield Farm to earn HERO.

Please note on OEC,  HERO -&gt; GLORY, ZENNY -&gt; ZENI

On Polygon: HERO -&gt; HONOR, ZENNY -&gt; ZENY.

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

