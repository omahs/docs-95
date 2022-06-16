# Protocols

## List

In order to fetch all protocols that are supported by defitrack, the following code can be used. The result is of type **Array<**[**Protocol**](domain/protocol.md)**>.**

```
import defitrack from "@defitrack/js-client";

const protocols = await defitrack.protocols().list()
```
