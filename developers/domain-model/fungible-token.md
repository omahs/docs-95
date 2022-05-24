---
description: A data type used to create a readable variant of a fungible token
---

# Fungible Token



```
class FungibleToken(
    val address: String,
    val name: String,
    val decimals: Int,
    val symbol: String,
    val logo: String?,
    val type: TokenType
)
```
