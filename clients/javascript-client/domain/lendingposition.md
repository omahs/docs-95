# LendingPosition

Lending Position is an extension of a [LendingMarket](lendingmarket.md) with the addition of an amount for a certain user.

```
export type LendingPosition = LendingMarket & {
    amount: Big
}
```
