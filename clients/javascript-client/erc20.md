---
description: Various api endpoints to fetch ERC20-related token information.
---

# 🪙 ERC20



### Fetch wrapped token address

Each native token on a specific network has a wrapped version that can be used. We keep a mapping of every wrapped token version of the native token on a chain.&#x20;

```
import defitrack from "@defitrack/js-client";

const wrappedToken: TokenInformation = await defitrack.erc20().wrapped("ETHEREUM")
```

### Fetch ERC20 Token Information

```
import defitrack from "@defitrack/js-client";

const token: TokenInformation = await defitrack.erc20().info("0xc5102fe9359fd9a28f877a67e36b0f050d81a3cc");
```

### Fetch Token  Balance for user

```
import defitrack from "@defitrack/js-client";

const token: TokenInformation = await defitrack.erc20().info("0xc5102fe9359fd9a28f877a67e36b0f050d81a3cc");
const balance = token.balanceOf("0x715beae184768766c65d8ed4aa6d1f6893efb542");
```
