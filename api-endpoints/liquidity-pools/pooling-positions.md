---
description: >-
  Our Pooling Positions module provides an easy way to get a user's position
  relative to a specific protocol. An aggregated position endpoint is not
  available due to response times.
---

# 🩱 Pooling Positions

## Fetch Pooling Positions for a user

Return a list of all pooling positions for a specific user on a specific protocol. The result is of type Array<[PoolingPosition](../../developers/domain-model/pooling/pooling-position.md)>.&#x20;

If the protocol does not support Pooling Markets, the result will be an empty Array.&#x20;

{% hint style="info" %}
Example fetching pooling positions for set protocol: [https://api.decentri.fi/set/pooling/0xf18adf71266411FF39FfC268843c9A64b3292d86/positions](https://api.decentri.fi/set/pooling/0xf18adf71266411FF39FfC268843c9A64b3292d86/positions)
{% endhint %}

{% swagger method="get" path="/{protocol}/pooling/{address}/positions" baseUrl="https://api.decentri.fi" summary="Get the pooling positions pertaining to a specific user for a specific protocol" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="protocol" type="string" required="true" %}
Slug of a protocol. Ex: quickswap
{% endswagger-parameter %}

{% swagger-parameter in="path" name="address" type="string" required="true" %}
wallet address
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Set Protocol Example" %}
```javascript
[
  {
    lpAddress: "0xf287d97b6345bad3d88856b26fb7c0ab3f2c7976",
    amountDecimal: 0.000019648543802574,
    amount: 19648543802574,
    name: "MATIC 2x Flexible Leverage Index",
    breakdown: [ ],
    network: {
      name: "POLYGON",
      logo: "https://github.com/defitrack/data/raw/master/logo/network/polygon.png",
      chainId: 137
    },
    symbol: "MATIC2x-FLI-P",
    protocol: {
      name: "SET",
      logo: "https://github.com/defitrack/data/raw/master/logo/protocol/set.png",
      slug: "set",
      primitives: [
        "POOLING"
      ],
      website: "https://setprotocol.com",
      company: {
        name: "Set Protocol",
        slug: "set"
      }
    },
    dollarValue: 0.00010922986598863365,
    id: "lp_polygon-set-0xf287d97b6345bad3d88856b26fb7c0ab3f2c7976",
    exitPositionSupported: false,
    marketType: "pooling",
    market: {
      id: "lp_polygon-set-0xf287d97b6345bad3d88856b26fb7c0ab3f2c7976",
      name: "MATIC 2x Flexible Leverage Index",
      protocol: {
        name: "SET",
        logo: "https://github.com/defitrack/data/raw/master/logo/protocol/set.png",
        slug: "set",
        primitives: [
          "POOLING"
        ],
        website: "https://setprotocol.com",
        company: {
          name: "Set Protocol",
          slug: "set"
        }
      },
      network: {
        name: "POLYGON",
        logo: "https://github.com/defitrack/data/raw/master/logo/network/polygon.png",
        chainId: 137
      },
      tokens: [
        {
          address: "0x8df3aad3a84da6b69a4da8aec3ea40d9091b2ac4",
          name: "Aave Matic Market WMATIC",
          decimals: 18,
          symbol: "amWMATIC",
          logo: "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/polygon/assets/0x8dF3aad3a84da6b69A4DA8aeC3eA40d9091B2Ac4/logo.png",
          type: "SINGLE",
          totalSupply: 1.518154547605509e+25
        },
        {
          address: "0x2791bca1f2de4661ed88a30c99a7a9449aa84174",
          name: "USD Coin (PoS)",
          decimals: 6,
          symbol: "USDC",
          logo: "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/polygon/assets/0x2791Bca1f2de4661ED88A30C99A7a9449Aa84174/logo.png",
          type: "SINGLE",
          totalSupply: 618231915874673
        }
      ],
      breakdown: [ ],
      apr: null,
      address: "0xf287d97b6345bad3d88856b26fb7c0ab3f2c7976",
      decimals: 18,
      marketSize: 48021.93412856235,
      prepareInvestmentSupported: false,
      exitPositionSupported: false,
      erc20Compatible: true,
      price: 5.559183779020016,
      totalSupply: 8638.306635911891,
      metadata: { },
      updatedAt: 1688122170196,
      marketType: "pooling"
    }
  }
]
```
{% endswagger-response %}
{% endswagger %}
