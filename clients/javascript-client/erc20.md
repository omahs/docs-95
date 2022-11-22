---
description: Various api endpoints to fetch ERC20-related token information.
---

# 🪙 ERC20

### Fetch wrapped token address

Each native token on a specific network has a wrapped version that can be used. We keep a mapping of every wrapped token version of the native token on a chain. The return value of the function is of type [TokenInformation](domain/tokeninformation.md).

```
import defihub from "@decentri.fi/defi-hub";

const wrappedToken: TokenInformation = await defihub.erc20().wrapped("ETHEREUM")
```

### Fetch ERC20 Token Information

Fetch the information of an erc20 token. The return value of the function is of type [TokenInformation](domain/tokeninformation.md).

```
import defihub from "@decentri.fi/defi-hub";

const token: TokenInformation = await defihub.erc20().info("0xc5102fe9359fd9a28f877a67e36b0f050d81a3cc");
```

### Fetch Token  Balance for user

```
import defihub from "@decentri.fi/defi-hub";

const token: TokenInformation = await defihub.erc20().info("0xc5102fe9359fd9a28f877a67e36b0f050d81a3cc");
const balance = token.balanceOf("0x715beae184768766c65d8ed4aa6d1f6893efb542");
```
