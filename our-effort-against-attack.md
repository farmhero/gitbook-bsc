# Our Effort Against Attack

Recently we are aware of frequent flash-loan attack on Binance Smart Chain network. While the team has taken extra caution reviewing our contract code base in-depth and consulted multiple professional security agencies, we have enforced the following to ensure safety of our contracts.

1. We have **prevented** contracts calling our contracts in our code, which will essentially eliminate the possibility of flash-loan attack because attackers has to call our contract using his/her own contract.
2. We are considering use delayed price feed.
3. We are considering to use multiple price oracle.





