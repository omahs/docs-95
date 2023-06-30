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
    val prepareInvestmentSupported: Boolean,
    val exitPositionSupported: Boolean,
    val erc20Compatible: Boolean,
    val price: BigDecimal,
    val totalSupply: BigDecimal,
    val metadata: Map<String, Any>,
    val updatedAt: Long,
    val deprecated: Boolean
)
```
