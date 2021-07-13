---
description: 'An algorithmic stablecoin, variant from Amplforth'
---

# ZENY

## Initial Supply

Initial supply of ZENY is 1,000,000,000,000,000. The initial supply is **timelocked** in treasury contract.

There will be no extra mint for ZENY. The initial supply is huge because the total supply will decrease when it deflates. The amount of initial supply does not affect circulating supply nor token price. 

This is what Amplforth has done, it has proven to be successful. 

## Initial Circulating Supply

The initial circulating of ZENY is 1000, the 1000 ZENY + 1000 USDC LP is added to initial liquidity pool.This ZENY-USDC-LP will be transferred to the dead address.

## Rebase: Elastic Supply

1. There will be 2 pools in boardroom, X3 and X7 pool. 

   A. X3 pool can be freely entered or exited, it shares 30% of all inflation rewards.

   B. X7 pool funds will be locked for 49 hours on each inflation. 

   C. Rewards can be claimed anytime. If ever a deflation happens, unclaimed rewards will be zero-out. Be sure to claim in time.

2. Rebase will adjust the circulation supply of ZENY to the 12-hour time weighted average price \(12-hour TWAP\).  
3. Rebase time: 02:00 and 14:00 UTC time, daily.
4. Oracle: QuickSwap Oracle at the moment. Will add multiple oracle later to increase stability. 
5. On each rebase, 10% of inflation amount will be sent to Seigniorage contract. The contract will sell the ZENY into USDC at inflation and will used to buy back ZENY in times of price drop.

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

