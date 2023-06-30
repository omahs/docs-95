# PoolingPosition

```
export type PoolingPosition = PoolingMarket & {
    amountDecimal: Big;
    amount: Big;
}
```

A Pooling Position is an extension of a [PoolingMarket](poolingmarket.md) with the addition of an amount for a certain user.
