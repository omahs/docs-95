# Adding New Markets

Adding a new market is a pretty straightforward endeavor. First, head over to our [github.](https://github.com/defitrack) [Defitrack Core](https://github.com/defitrack/defitrack-core) is the code that powers the API. It contains all code specific to [protocols](https://github.com/defitrack/defitrack-core/tree/main/defitrack-protocols) and [networks](https://github.com/defitrack/defitrack-core/tree/main/defitrack-blockchains). Furthermore, it contains rest APIs for [each and every supported protocol, as well as a few generic features (like prices, erc20, abi, etc...)](https://github.com/defitrack/defitrack-core/tree/main/defitrack-rest).&#x20;

Adding a new market, be it Lending, Pooling or Farming, consists of following these basic steps.

### Fork the repository

![](../../.gitbook/assets/Screenshot\_20220530\_092551.png)

First off, fork the repository. You'll work by creating a fork, working on said fork and creating a pull request. We'll review the changes and will work together, in an async fashion towards a solution.

We'd love it if you could star the repo in the meantime in order to get more eyes on the project.

### Adding a new protocol (optional)&#x20;

#### protocol code

A protocol is an application or Defi native protocol, like [compound](https://compound.finance/), [uniswap](https://uniswap.org/) or [beefy finance](https://beefy.finance/). Markets always belong to protocols. If the protocol you want to add does not exist in defitrack yet, you'll have to add it. Currently supported protocols can be found on our [roadmap](../../general/supported-protocols/).

You can look at the examples under [**defitrack-protocols**](https://github.com/defitrack/defitrack-core/tree/main/defitrack-protocols) to get a feel of the existing structure. The core code of the specific protocol belongs here. Contract calls or graph protocol fetching is what needs to be added here. Don't forget to add the protocol to [**defitrack-protocol/protocol-dependencies**/**pom.xml**](https://github.com/defitrack/defitrack-core/tree/main/defitrack-protocols/protocol-dependencies/pom.xml)**.**&#x20;

#### **protocol api**

Next up, you'll be creating a new api microservice under [**defitrack-rest/defitrack-protocol-services**](https://github.com/defitrack/defitrack-core/tree/main/defitrack-rest/defitrack-protocol-services)**.** You can visit the existing APIs to see what the structure and pom.xml looks like.&#x20;

#### ci

In order for our ci to automatically deliver a docker image containing the code, you'll have to add the protocol to **ci/protocols.txt.**

**logo**

[clone the data repository](https://github.com/defitrack/data) and add the logo of the protocol to **logos/.** Remember the name and the extension.

**enumeration**

Defitrack core contains an enum called **Protocol.** Add the protocol to this enum. The logo is the one you added in the previous step.

### Adding Pooling Markets

If you'd like to add new Pooling markets, like the ones on [Curve](https://github.com/defitrack/defitrack-core/blob/main/defitrack-rest/defitrack-protocol-services/defitrack-curve/src/main/java/io/defitrack/protocol/curve/staking/CurveEthereumPoolingMarketService.kt) or [Uniswap](https://github.com/defitrack/defitrack-core/blob/main/defitrack-rest/defitrack-protocol-services/defitrack-uniswap/src/main/java/io/defitrack/protocol/uniswap/pooling/UniswapEthereumPoolingMarketService.kt), you'll need to create a new implementation of [**PoolingMarketService**](https://github.com/defitrack/defitrack-core/blob/main/defitrack-rest/defitrack-api/src/main/java/io/defitrack/pool/PoolingMarketService.kt)**.**&#x20;

The [domain model ](../domain-model/)for [Pooling Markets](../domain-model/pooling-market.md) consists of the following fields:

<table><thead><tr><th width="153.33333333333331">field</th><th width="166.36144578313258">type</th><th>description</th></tr></thead><tbody><tr><td>id</td><td>string</td><td>unique id per market. Make it something logical like quickwap-polygon-$address</td></tr><tr><td>address</td><td>string</td><td>address of the LP token</td></tr><tr><td>name</td><td>string</td><td>name of the market, like <strong>Curve.fi DAI/USDC/USDT/PAX.</strong></td></tr><tr><td>protocol</td><td>Protocol</td><td>One of the protocols in the enum, like <strong>CURVE</strong></td></tr><tr><td>network</td><td>Network</td><td>One of the networks in the enum, like <strong>POLYGON</strong></td></tr><tr><td>tokens</td><td><a href="../domain-model/fungible-token.md">FungibleToken</a>[]</td><td>a list of underlying tokens</td></tr><tr><td>apr</td><td>Double</td><td>The APR of the LP in percentage. 0.5 = 0.5%</td></tr></tbody></table>

### Adding **Farming** Markets

If you'd like to add new Farming markets, like the ones on [Dinoswap](https://github.com/defitrack/defitrack-core/blob/main/defitrack-rest/defitrack-protocol-services/defitrack-dinoswap/src/main/java/io/defitrack/protocol/dinoswap/staking/DinoswapStakingMarketService.kt) or Convex, you'll need to create a new implementation of [**StakingMarketService**](https://github.com/defitrack/defitrack-core/blob/main/defitrack-rest/defitrack-api/src/main/java/io/defitrack/staking/StakingMarketService.kt)**.**

### **Adding Lending Markets**

If you'd like to add new Lending markets, like the ones on [Compound](https://github.com/defitrack/defitrack-core/blob/main/defitrack-rest/defitrack-protocol-services/defitrack-compound/src/main/java/io/defitrack/protocol/compound/lending/CompoundLendingMarketService.kt) or [Aave](https://github.com/defitrack/defitrack-core/blob/main/defitrack-rest/defitrack-protocol-services/defitrack-aave/src/main/java/io/defitrack/protocol/aave/v3/lending/market/AaveV3OptimismLendingMarketProvider.kt), you'll need to create a new implementation of [**LendingMarketService**](https://github.com/defitrack/defitrack-core/blob/main/defitrack-rest/defitrack-api/src/main/java/io/defitrack/lending/LendingMarketService.kt)**.**&#x20;
