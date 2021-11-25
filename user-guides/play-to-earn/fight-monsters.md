# Fight Monsters

**How to Fight Monsters**

You need to use ‘Rounds’ to fight monsters. Your Hero will auto recover 1 round every 4 hours. The rarity of your hero determines the maximum rounds accumulated for your hero.&#x20;

```
Max Rounds for the Hero = Number of Stars -1. 
```

So if you have a 6 star Hero, you can accumulate 5 rounds per day. For a 2 star hero, you need to fight every 4 hours so you do not waste your rounds.

#### HP

Each Hero has a HP (Health Point) according to its rarity.

| Rarity | HP  |
| ------ | --- |
| 2 Star | 50  |
| 3 Star | 100 |
| 4 Star | 150 |
| 5 Star | 200 |
| 6 Star | 250 |

#### Monster's Attack

Each Monster has a Base ATK (attack) Point and a Critical Point. Currently there is a 20% fluctuation for the base attack, and the critical harm Multiple is 5x.&#x20;

During battle, the actual harm created from base attack will be base attack + critical harm.

```
Base Harm = (0.8 ~ 1.2) * Base ATK
Critical Harm = 5 * Base ATK
The chance for trigger an critical attack is 1% - 4%.
Harm = Base Harm + Critical Harm (if any) 
```

| Monster | Base ATK | Critical |
| ------- | -------- | -------- |
| Solider | 20       | 1%       |
| Wizard  | 30       | 2%       |
| General | 40       | 3%       |
| KING    | 50       | 4%       |

#### Reward

The win rate against the monsters are fixed at the moment. The Hero’s Hashrate determines the reward you can get.&#x20;

```
Winning Reward = Hero's Hashrate * Reward Multiple
```

#### Early Exit Fee

There will be a 15% early exit fee for claiming the fight rewards. But later this week we will be able to reveal a feature that you can use the fight reward to get Loot Boxes. If you want to claim the reward in full, the vesting time is 4 days.

Each new reward will rest the vesting timer back to 4 days.
