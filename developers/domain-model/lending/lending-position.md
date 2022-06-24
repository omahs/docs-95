# Lending Position

```
data class LendingPosition(
    val id: String,
    val network: NetworkVO,
    val protocol: ProtocolVO,
    val dollarValue: Double,
    val rate: Double?,
    val name: String,
    val amount: Double,
    val token: FungibleToken
)
```
