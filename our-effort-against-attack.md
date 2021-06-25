# Our Effort Against Attack

Recently we are aware of frequent flash-loan attack on Binance Smart Chain network. While the team has taken extra caution reviewing our contract code base in-depth and consulted multiple professional security agencies, we have enforced the following to ensure safety of our contracts.

1. We have **prevented** contracts calling our contracts in our code, which will essentially eliminate the possibility of flash-loan attack because attackers has to call our contract using his/her own contract.
2. We are considering use delayed price feed.
3. We are considering to use multiple price oracle.

## A notes on FarmHero upgradable contracts and timelocks 

We have witnessed several project, including uranium on Binance Smart Chain, bunny, who have smart contract design bug found but not able to fix timely, which caused lost of client funds. It's to our best interest to protect the funds safety so we deploy our contracts using upgradable proxy. Also it worths mention that mature team such as cream.finance and pancake have migrated their contracts to upgradable as well. 

### MasterChef

We have timelocked \(48 hrs\) our MasterChef contract by tx:

[https://polygonscan.com/tx/0x604d2c90d8150646cedb02db5529815f829f9fffe5422d63689b6c732c8d3427](https://polygonscan.com/tx/0x604d2c90d8150646cedb02db5529815f829f9fffe5422d63689b6c732c8d3427)

### Game Contracts

These contracts does **not** hold any client fund but only pot prize. Also game rules are subject to change according to community opinions. We deploy them using upgradable proxy. 

### Staking Contract

We forked it from EPS project on bsc. It stakes USDc rewards to $HONOR holders $HONOR and we will add **timelocks to the proxy owner** once our protocol goes into stable mode.





