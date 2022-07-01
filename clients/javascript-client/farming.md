# 🐄 Farming

### List markets by protocol

In order to list all lending markets for a specific protocol the following code can be used. The return value is of type **Array<**[**FarmingMarket**](domain/farmingmarket.md)**>.**&#x20;

{% hint style="info" %}
If the protocol does not support farming markets, an empty array will be returned.
{% endhint %}

```
import defitrack from "@defitrack/js-client";

const markets = await defitrack.farming().markets("beefy")
```

### Get user positions for by protocol

```
import defitrack from "@defitrack/js-client";

const positions: Array<LendingPosition> = await defitrack.farming().positions("beefy","0x715beae184768766c65d8ed4aa6d1f6893efb542");
```

