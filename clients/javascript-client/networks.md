# Networks

## List

In order to fetch all networks that are supported by defitrack, the following code can be used. The result is of type **Array<**[**Network**](domain/network.md)**>.**

```
import defihub from "@decentri.fi/defi-hub";

const networks = await defihub.networks().list()
```
