# Networks

## List

In order to fetch all networks that are supported by defitrack, the following code can be used. The result is of type **Array\<Network>.**

```
import defitrack from "./index";
import {Network} from "./network/network.model";

const networks: Array<Network> = await defitrack.networks().list()
```
