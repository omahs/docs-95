# Pooling Market

```
data class PoolingMarket(
    val id: String,
    val address: String,
    val name: String,
    val protocol: ProtocolVO,
    val network: NetworkVO,
    val tokens: List<FungibleToken>,
    val apr: BigDecimal?,
    val marketSize: BigDecimal?,
)
```
