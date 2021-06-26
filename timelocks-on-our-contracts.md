# Timelocks on our Contracts

Recently we are aware of frequent flash-loan attack on Binance Smart Chain network. While the team has taken extra caution reviewing our contract code base in-depth and consulted multiple professional security agencies, we have enforced the following to ensure safety of our contracts.

1. We have **prevented** contracts calling our contracts in our code, which will essentially eliminate the possibility of flash-loan attack because attackers has to call our contract using his/her own contract.
2. We are considering use delayed price feed.
3. We are considering to use multiple price oracle.

## A notes on FarmHero upgradable contracts and timelocks 

We have witnessed several project, including uranium on Binance Smart Chain, bunny, who have smart contract design bug found but not able to fix timely, which caused lost of client funds. It's to our best interest to protect the funds safety so we deploy our contracts using upgradable proxy. Also it worths mention that mature team such as cream.finance and pancake have migrated their contracts to upgradable as well. 

### MasterChef

We have timelocked \(48 hrs\) our MasterChef contract's Proxy Admin by setting the owner of the ProxyAdmin contract to the timelock contract. Therefore, any execution to update the masterchef contract will be delaying 48 hours on chain. 

| Contract | Address |
| :--- | :--- |
| ProxyAdmin | 0xC7251aD96Df7877Afc3C3AF533B4227604b5e70A |
| Timelock \(48 hrs\) | 0x09dE73dD716047C4586ec18280Af312B1B92fE7C |
| MasterChef \(Yield Farm\) | 0x8e5860DF653A467D1cC5b6160Dd340E8D475724E |

#### How to Verify:

1. You can check the current ProxyAdmin of our MasterChef Contract [Here via PolygonScan](https://polygonscan.com/address/0xC7251aD96Df7877Afc3C3AF533B4227604b5e70A#readContract): put in our masterchef contract address and try get ProxyAdmin, you will see that currently the proxyAdmin of our masterChef contract is indeed 0xC7251aD96Df7877Afc3C3AF533B4227604b5e70A.

![](.gitbook/assets/image%20%282%29.png)

2. Also scroll down you can see that the owner of this ProxyAdmin is 0x09dE73dD716047C4586ec18280Af312B1B92fE7C, which is our timelock contract.

![](.gitbook/assets/image%20%283%29.png)

3. Click in to the [Timelock contract](https://polygonscan.com/address/0x09de73dd716047c4586ec18280af312b1b92fe7c#readContract), you can see that current delay is 172800 seconds, which is 48 hours.

![](.gitbook/assets/image%20%284%29.png)

### Game Contracts

These contracts does **not** hold any client fund but only pot prize. Also game rules are subject to change according to community opinions. We deploy them using upgradable proxy. 

### Staking Contract

We forked it from EPS project on bsc. It stakes USDc rewards to $HONOR holders $HONOR and we will add **timelocks to the proxy owner** once our protocol goes into stable mode.





