# TokenInformation

```
export type TokenInformation = {
    logo?: string,
    name: string,
    symbol: string,
    address: string,
    decimals: number,
    totalSupply: BigInteger,
    underlyingTokens: Array<TokenInformation>,
    protocol?: Protocol,
    network: Network,
    balanceOf: Function
}
```
