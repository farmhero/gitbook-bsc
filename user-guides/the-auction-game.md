# The Auction Game

In the Auction Game, users will use $HERO token to bid for the BUSD pot. Those BUSD are partial sales from vaults. For more details regarding the BUSD pool, read the farming page.

{% page-ref page="farming-usdhero-token/yield-farming.md" %}

## Bid Rules

* Initial Minimum bid price is 0.01 $HERO, after that, next minimum bid price will be calculated based on _minimum increment percentage_ and _minimum increment amount._ 

```text
next min. bid = min(bid * min.increment.pct, min.increment.amt) + bid
```

* A bid is valid when it is higher than next minimum bid. 
* The $HERO used to bid against the BUSD pot will be immediately **burned**. That means, either one user wins or not, the bid amount will **NOT** be returned. Please take caution when joining. 
* During each round, one user can raise his/ her bid multiple times. He/ She will only need to pay the increment amount. 

## Auction Ends Rules \(Pot distribution\)

* There will be a round countdown timer for the auction game, initially started with 5 minutes. When the timer counts down to 0, the auction ends. The last bidder will win. Each successful bid will add 1 minute to the round timer, to a hard cap of 15 minutes. 
* On each round end, 80% of the BUSD pot will be sent to the last bidder, 20% of the pot will be rolled over to the next round.
* A round is preceded with a 5-minute starting grace period when bids are not permitted. This is to help users to know what is going on and get ready for next round.

