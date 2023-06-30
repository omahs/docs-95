# FarmingMarket

```
export type FarmingMarket = {
    id: string,
    network: Network,
    protocol: Protocol,
    name: string,
    stakedToken: FungibleToken,
    rewardTokens: Array<FungibleToken>,
    contractAddress: string, //deprecated
    vaultType: string,
    marketSize: Big | null,
    apr: Big | null,
    prepareInvestmentSupported: boolean
    exitPositionSupported: boolean
    marketType: string
}
```
