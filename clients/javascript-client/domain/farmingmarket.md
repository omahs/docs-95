# FarmingMarket

```
type FarmingMarket = {
    id: string,
    network: Network,
    protocol: Protocol,
    name: string,
    stakedToken: FungibleToken,
    reward: Array<FungibleToken>,
    contractAddress: string, //deprecated
    vaultType: string,
    marketSize: Big | null,
    apr: Big | null,
    prepareInvestmentSupported: boolean
    marketType: string
}
```
