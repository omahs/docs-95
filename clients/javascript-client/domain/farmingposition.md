# FarmingPosition

```
export type FarmingPosition = FarmingMarket & {
    stakedAmount: Big;
    stakedAmountDecimal: Big;
    tokenAmount: Big;
    tokenAmountDecimal: Big;
}
```

A Farming Position is an extension of a [FarmingMarket](farmingmarket.md) with the addition of an amount for a certain user.
