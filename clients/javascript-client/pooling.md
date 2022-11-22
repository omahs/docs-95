# 🏊♂ Pooling

### List markets by protocol

In order to list all lending markets for a specific protocol the following code can be used. The return value is of type **Array<**[**PoolingMarket**](domain/poolingmarket.md)**>.**&#x20;

{% hint style="info" %}
If the protocol does not support pooling markets, an empty array will be returned.
{% endhint %}

```
import defihub from "@decentri.fi/defi-hub";

const markets = await defihub.pooling().markets("balancer")
```

### Get user positions for by protocol

```
import defihub from "@defitrack/js-client";

const positions: Array<LendingPosition> = await defihub.pooling().positions("curve","0x715beae184768766c65d8ed4aa6d1f6893efb542");
```
