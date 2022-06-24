# Lending Market

```
data class LendingMarketVO(
    val id: String,
    val name: String,
    val protocol: ProtocolVO,
    val network: NetworkVO,
    val token: FungibleToken,
    val rate: Double?,
    val poolType: String,
    val marketSize: BigDecimal?,
    val prepareInvestmentSupported: Boolean
)
```
