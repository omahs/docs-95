# Token Information

```
class TokenInformation(
    val logo: String? = null,
    val name: String,
    val symbol: String,
    val address: String,
    val decimals: Int,
    val type: TokenType,
    val totalSupply: BigInteger = BigInteger.ZERO,
    val underlyingTokens: List<TokenInformation> = emptyList(),
    val protocol: Protocol? = null
) 
```
