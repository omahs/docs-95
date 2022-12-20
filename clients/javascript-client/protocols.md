# Protocols

## List

In order to fetch all protocols that are supported by defitrack, the following code can be used. The result is of type **Array<**[**Protocol**](domain/protocol.md)**>.**

```
import defihub from "@decentri.fi/defi-hub";

const protocols = await defihub.protocols().list()
```
