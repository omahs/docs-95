# Common Code Snippets

### Calculate a price

Calculating a price is pretty easy if you use our internal price api.

```
import io.defitrack.price.PriceResource

//autowire
private val priceResource: PriceResource

val price: Double = priceResource.calculatePrice(
    PriceRequest(
        "0x2d94aa3e47d9d5024503ca8491fce9a2fb4da198",
        Network.ETHEREUM,
        0.3.toBigDecimal(),
        TokenType.SINGLE
    )
)
```

### Fetch an ABI

You can use the abiResource to fetch an ABI. This will get the ABI straight from our abi rest api.

```
import io.defitrack.abi.ABIResource

//autowire
private val abiResource: ABIResource

val abi: String = abiResource.getABI("aave/LendingPoolAddressesProvider.json")
```

### Fetch Token Information

Fetching token information can be done using the erc20Resource. The result of this call will be of type [TokenInformation](../domain-model/token-information.md).

```
import io.defitrack.token.ERC20Resource

//autowire
private val erc20Resource: ERC20Resource

val tokenInfo: TokenInformation = erC20Resource.getTokenInformation(Network.ETHEREUM, "0x2d94aa3e47d9d5024503ca8491fce9a2fb4da198")
```
