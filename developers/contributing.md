# Contributing

So you're a developer and would like to contribute to Defitrack? Entirely possible! Defitrack could be the ideal way for developers who are into JVM languages (Like Kotlin and Java) to learn about Defi and Web3 in general.

## Java vs Kotlin

When contributing, we opt for developers to use the [Kotlin Programming Language](https://kotlinlang.org/). However, should you not be proficient in Kotlin, but have a strong base in Java, we allow java contributions. We realize a lot of developers have years of hand on experience in JVM, with Java being the main programming language of these developers.&#x20;

We appreciate any contribution to the general defitrack api. It's possible your Java code might get refactored to Kotlin in the future, but we much more value your contribution than being Kotlin purebreds.&#x20;

All we ask is to adhere to the existing interfaces defined in the [domain model section](domain-model/).

## Adding a new market

Adding a new market is a pretty straightforward endeavour. First, head over to our [github.](https://github.com/defitrack) [Defitrack Core](https://github.com/defitrack/defitrack-core) is the code that powers the API. It contains all code specific to [protocols](https://github.com/defitrack/defitrack-core/tree/main/defitrack-protocols) and [networks](https://github.com/defitrack/defitrack-core/tree/main/defitrack-blockchains). Furthermore, it contains rest APIs for [each and every supported protocol, as well as a few generic features (like prices, erc20, abi, etc...)](https://github.com/defitrack/defitrack-core/tree/main/defitrack-rest).&#x20;

Adding a new market, be it Lending, Pooling or Farming, consists of following these basic steps.

### Fork the repository

![](../.gitbook/assets/Screenshot\_20220530\_092551.png)

First off, fork the repository. You'll work by creating a fork, working on said fork and creating a pull request. We'll review the changes and will work together, in an async fashion towards a solution.

We'd love it if you could star the repo in the meantime in order to get more eyes on the project.

### Adding a new protocol (optional)&#x20;

A protocol is an application or defi native protocol, like compound, uniswap or beefy finance. Markets always belong to protocols. If the protocol you want to add does not exist in defitrack yet, you'll have to add it.

You can look at the examples under [**defitrack-protocols**](https://github.com/defitrack/defitrack-core/tree/main/defitrack-protocols) to get a feel of the existing structure. The core code of the specific protocol belongs here. Contract calls or graph protocol fetching is what belongs here. Don't forget to add the protocol to [**defitrack-protocol/protocol-dependencies**/**pom.xml**](https://github.com/defitrack/defitrack-core/tree/main/defitrack-protocols/protocol-dependencies/pom.xml)**.**&#x20;

Next up, you'll be creating a new api microservice under [**defitrack-rest/defitrack-protocol-services**](https://github.com/defitrack/defitrack-core/tree/main/defitrack-rest/defitrack-protocol-services)**.** You can take a visitthe existing APIs to see what the structure and pom.xml looks like.&#x20;

### Adding Pooling Markets

If you'd like to add new Pooling markets, like the ones on Curve or Uniswap, you'll need to create a new implementation of [**PoolingMarketService**](https://github.com/defitrack/defitrack-core/blob/main/defitrack-rest/defitrack-api/src/main/java/io/defitrack/pool/PoolingMarketService.kt)**.**&#x20;

### Adding **Farming** Markets

If you'd like to add new Farming markets, like the ones on Dinoswap or Convex, you'll need to create a new implementation of **** [**StakingMarketService**](https://github.com/defitrack/defitrack-core/blob/main/defitrack-rest/defitrack-api/src/main/java/io/defitrack/staking/StakingMarketService.kt)**.**

### **Adding Lending Markets**

If you'd like to add new Lending markets, like the ones on Compound or Aave, you'll need to create a new implementation of **** [**LendingMarketService**](https://github.com/defitrack/defitrack-core/blob/main/defitrack-rest/defitrack-api/src/main/java/io/defitrack/lending/LendingMarketService.kt)**.**&#x20;

****
