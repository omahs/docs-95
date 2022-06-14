# Contribution Guide

So you're a developer and would like to contribute to Defitrack? Entirely possible! Defitrack could be the ideal way for developers who are into JVM languages (Like Kotlin and Java) to learn about Defi and Web3 in general.

If you have any questions, feel free to reach out in our [developer channel on our fresh discord](https://discord.gg/stA5cN69sZ).&#x20;

## Java vs Kotlin

When contributing, we opt for developers to use the [Kotlin Programming Language](https://kotlinlang.org/). However, should you not be proficient in Kotlin, but have a strong base in Java, we allow java contributions. We realize a lot of developers have years of hand on experience in JVM, with Java being the main programming language of these developers.&#x20;

We appreciate any contribution to the general defitrack api. It's possible your Java code might get refactored to Kotlin in the future, but we much more value your contribution than being Kotlin purebreds.&#x20;

All we ask is to adhere to the existing interfaces defined in the [domain model section](../domain-model/).

****

## **Repositories**

### **Defitrack Core**

[This repository](https://github.com/defitrack/defitrack-core) contains all the code powering the API. It contains the code to interact with networks, protocols and provides abstractions of common concepts (such as [ERC20](https://github.com/defitrack/defitrack-core/tree/main/defitrack-rest/defitrack-erc20), [prices](https://github.com/defitrack/defitrack-core/tree/main/defitrack-rest/defitrack-price), [ABIs](https://github.com/defitrack/defitrack-core/tree/main/defitrack-rest/defitrack-abi))

![](../../.gitbook/assets/code-layout.png)

### **Defitrack Data**

[This repository](https://github.com/defitrack/data) contains all data underlying data that is required to populate markets. Data that can be stored here are for example:

* ABIs
* Token lists
* Logos
* Contract addresses
