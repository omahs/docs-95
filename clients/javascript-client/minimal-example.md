---
description: A little example of using Decentrifi's defi hub's javascript client.
---

# Minimal Example

### Import the package

```
import defihub from '@decentri.fi/defi-hub'
```

### Printing all the supported protocols

```
export const printProtocols = async () => {
    const protocols = await defihub.protocols().list();
    console.log(protocols);
}

printProtocols();
```
