# Protocols

## List

In order to fetch all protocols that are supported by defitrack, the following code can be used:

```
import defitrack from "./index";
import {Protocol} from "./protocol/protocol.model";

const protocols: Array<Protocol> = await defitrack.protocols().list()
```
