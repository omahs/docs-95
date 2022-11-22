---
description: A little example of using defitrack defi hub's javascript client.
---

# Minimal Example

### Import the package

```
import defitrack from '@defitrack/js-client'
```

### Printing all the supported protocols

```
export const printProtocols = async () => {
    const protocols = await defitrack.protocols().list();
    console.log(protocols);
}

printProtocols();
```
