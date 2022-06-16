# PoolingMarket

```
type PoolingMarket = {
    id: string,
    address: string,
    name: string,
    protocol: Protocol,
    network: Network,
    tokens: Array<FungibleToken>,
    apr: Big | null,
    marketSize: Big | null,
    prepareInvestmentSupported: boolean
    marketType: string,
}
```
