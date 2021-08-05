# Timelock on Our Contracts

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
| ProxyAdmin | 0x53DeD22F02789B6811E10c5326730E62Cb328Cf9 |
| Timelock \(48 hrs\) | 0x32A67309C356D8Db401eb159Bca11aDc6a48cae0 |
| MasterChef \(Yield Farm\) | 0xDAD01f1d99191a2eCb78FA9a007604cEB8993B2D |
| Hero \(token\) | 0x9B26e16377ad29A6CCC01770bcfB56DE3A36d8b2 |

#### How to Verify:

1. You can check the current ProxyAdmin of our MasterChef Contract [here via BscScan](https://bscscan.com/address/0x53DeD22F02789B6811E10c5326730E62Cb328Cf9#readContract): put in our masterchef contract address and try get ProxyAdmin, you will see that currently the proxyAdmin of our masterChef contract is indeed 0x53DeD22F02789B6811E10c5326730E62Cb328Cf9.

![](.gitbook/assets/image%20%281%29.png)

1. Also scroll down you can see that the owner of this ProxyAdmin is 0x32A67309C356D8Db401eb159Bca11aDc6a48cae0, which is our timelock contract.

![](.gitbook/assets/image%20%282%29.png)

1. Click in to the [Timelock contract](https://bscscan.com/address/0x32a67309c356d8db401eb159bca11adc6a48cae0), you can see that current delay is 172800 seconds, which is 48 hours.

![](.gitbook/assets/image%20%283%29.png)

### Game Contracts

These contracts does **not** hold any client fund but only pot prize. Also game rules are subject to change according to community opinions. We deploy them using upgradable proxy.

### Staking Contract

We forked it from EPS project on bsc. It stakes USDc rewards to $HONOR holders $HONOR and we will add **timelocks to the proxy owner** once our protocol goes into stable mode.

\*\* attaching the latest transaction to change ProxyAdmin

[https://bscscan.com/tx/0x3e4d85349e3c7651c79a10efccc0e77e13a0019b9dd90f3eabab5d6715026e73](https://bscscan.com/tx/0x3e4d85349e3c7651c79a10efccc0e77e13a0019b9dd90f3eabab5d6715026e73)

[https://bscscan.com/tx/0xfd0160f302de3afee9ef3d8954b74a539bdb1a277c04af2a2453b7a7c09b5f74](https://bscscan.com/tx/0xfd0160f302de3afee9ef3d8954b74a539bdb1a277c04af2a2453b7a7c09b5f74)

