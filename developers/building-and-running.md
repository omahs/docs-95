---
description: A quick intro on how to build and run each module.
---

# Defitrack Core

## Building the project

You can build the entire project by running the following command. This requires maven and java 8+. You can also use the included maven wrapper. Please make sure the code successfully builds before requesting a review.

```
./mvnw clean install
```

## Running Protocol Microservices

Next to all the supporting microservices, like price-api, abi-api and erc20-api, there are microservices for every supported protocol. If you're using Intellij, you can use the run or debug the application straight from your IDE, like so:

![Running the Aave application. You can use the profile argument or add local to your active profiles.](../.gitbook/assets/Screenshot\_20220531\_132700.png)

We also added a convenient script to run a specific microservice. You can run it as follows:

```
./run-protocol aave
```

Just replace **aave** by the protocol you wish to spin up a microservice for.

There's no need to deploy any other service. Your protocol service will automatically connect to the live environment to fetch more data. You'll see the application populating its markets at startup.

![Populating caches might take up to a few minutes, depending on the amount of markets.](<../.gitbook/assets/Screenshot\_20220531\_134904 (1).png>)

## Testing out the running service

By default, the application will start up at **port 8081.** You can simply navigate to the following url to see if the service is running.

```
http://localhost:8081/actuator/health
```

You can then try out the different apis, like fetching [lending markets](../api-endpoints/lending.md), [pooling markets](../api-endpoints/pooling-markets.md) or [farming markets](../api-endpoints/farming.md), depending on which microservice you've deployed.
