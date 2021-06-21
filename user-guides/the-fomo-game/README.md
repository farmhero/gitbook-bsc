---
description: Salute to the Classic FOMO3D Game
---

# The Fomo Game

## Initial Liquidity

Upon genesis launch, the protocol will mint HONOR together with the same amount of Key and add them to QuickSwap, at this time, 1 KEY = 1 HONOR.

There is a 5% sale tax on $KEY. When you sell $KEY, 5% of the $KEY will be burnt. Because of the change, when selling $KEY, the slippage needs to be adjusted to at least 7%.

## Pot

The pot funds will be partial $Quick generated from vaults. For more details, check the farming page.

{% page-ref page="../farming-usdhero-token/yield-farming.md" %}

## Game Rules

\(The updated game rules are revised to make the game fairer and alleviate the bot's interference of the games' fairness.\)

Users can buy $Key using $Hero. They can purchase directly in the FarmHero App or on QuickSwap.

There is a countdown timer for each round. Initially the timer counts down from 24 hours.

User can deposit $Key to _add time to_ the countdown timer. Any $Key deposit with amount bigger than 1 _will add 30 seconds to timer, to a hardcap of 24 hours._

_Time is added per-key, rounded down, so 2.5 keys = 60 seconds._

_There is a max 1000 KEY per purchase to avoid whale front-run. This amount can be adjusted when the game is stable to make the purchase easier._

## **Rewards**

Deposited Keys grant instant dividends on all volume that flows through a round, meaning users will constantly receive a stream of passive income from the game as keys are bought until a round ends.

| Percentage | Usage of the deposited $KEY token |
| :--- | :--- |
| 50% | Burnt |
| 45% | Distributed to previous users who have deposited $KEY in current round |
| 5% | referral rewards |

## Round Ends \(Pot Distribution\)

The last player to have deposited at least 1 full key when the round timer completes its countdown, immediately drains 80% of the prize seen in the pot and ends the round. The last player and all people who have burnt Keys in the round will share the prize. The rest of the 20% prize pot will be carried over to next round.

| Usage | Percentage |
| :--- | :--- |
| Roll to Next Round | 20% |
| Winner \(last-key buyer\) | 30% |
| All Key Holders that burns Keys within the round | 50% |

A round is preceded with a 1-hour starting grace period when deposits are not permitted. This is to help users to know what is going on and get ready for next round.

## Resetting the KEY Price

Keys price will be reset on round ends. The FarmHero Protocol will use a 'reweight' mechanism to adjust the $KEY-$HONOR pair price on pancake back to 1 million KEY and 1 million HONOR . Extra $HONOR will be burnt.

