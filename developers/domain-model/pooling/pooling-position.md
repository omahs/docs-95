---
description: >-
  The concept of a pooling position is a position that someone has taking into a
  liquidity pool (market).
---

# Pooling Position

```
class PoolingPosition(
    val lpAddress: String,
    val amount: BigInteger,
    val amountDecimal: BigDecimal,
    val name: String,
    val network: NetworkVO,
    val symbol: String,
    val protocol: ProtocolVO,
    val dollarValue: Double,
    val id: String,
    val market: PoolingMarketVO
)
```
