# PoolingMarket

```
export type PoolingMarket = {
    id: string,
    address: string,
    name: string,
    protocol: Protocol,
    network: Network,
    tokens: Array<FungibleToken>,
    apr: Big | null,
    marketSize: Big | null,
    prepareInvestmentSupported: boolean
    exitPositionSupported: boolean
    marketType: string,
    decimals: number,
    erc20Compatible: boolean,
    price: Big,
    totalSupply: Big,
    metadata: Map<String, Object>,
    updatedAt: number
}
```
