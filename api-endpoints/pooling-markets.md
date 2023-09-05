# 🏊♂ Pooling Markets

Defitrack tracks various pooling markets across different chains. We try to maintain an up to date database of active and inactive markets in order to locate user funds, as well as locate opportunities.

### Fetching all supported markets for a specific protocol

Return a list of Pooling Markets, which contain information about which tokens can be put in a pool on a specific platform. It often returns the APR, which is the rate you get for providing your assets to the pool.&#x20;

{% hint style="info" %}
Example: [https://api.decentri.fi/quickswap/pooling/all-markets](https://api.decentri.fi/quickswap/pooling/markets)
{% endhint %}

{% swagger method="get" path="/{protocol}/pooling/all-markets" baseUrl="https://api.decentri.fi" summary="Fetches all staking markets for a specific protocol on a specific network. " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="protocol" required="true" %}


slug of the protocol
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="https://api.decentri.fi/quickswap/pooling/all-markets" %}
```javascript
[
  {
    id: "lp_polygon-quickswap-0xa19460a60cb48d8c5aaa10b874f7a908e0483ea5",
    name: "MODA/WETH LP",
    protocol: {
      name: "QUICKSWAP",
      logo: "https://github.com/defitrack/data/raw/master/logo/protocol/quickswap.png",
      slug: "quickswap",
      primitives: [
        "POOLING",
        "FARMING"
      ],
      website: "https://quickswap.exchange/",
      company: {
        name: "QuickSwap",
        slug: "quickswap"
      }
    },
    network: {
      name: "POLYGON",
      logo: "https://github.com/defitrack/data/raw/master/logo/network/polygon.png",
      chainId: 137
    },
    tokens: [
      {
        address: "0x5e430f88d1be82eb3ef92b6ff06125168fd5dcf2",
        name: "moda",
        decimals: 18,
        symbol: "MODA",
        logo: "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/polygon/assets/0x5E430F88D1BE82EB3eF92b6fF06125168fD5DCf2/logo.png",
        type: "SINGLE",
        totalSupply: 1.546349268715101e+23
      },
      {
        address: "0x7ceb23fd6bc0add59e62ac25578270cff1b9f619",
        name: "Wrapped Ether",
        decimals: 18,
        symbol: "WETH",
        logo: "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/polygon/assets/0x7ceB23fD6bC0adD59E62ac25578270cFf1b9f619/logo.png",
        type: "SINGLE",
        totalSupply: 2.1919744612287857e+23
      }
    ],
    breakdown: [],
    apr: 0.0135709114143661,
    address: "0xa19460a60cb48d8c5aaa10b874f7a908e0483ea5",
    decimals: 18,
    marketSize: 35910.31571922588,
    prepareInvestmentSupported: false,
    exitPositionSupported: false,
    erc20Compatible: true,
    price: 54.0706875173756,
    totalSupply: 664.1364733467854,
    metadata: {},
    updatedAt: 1688111739226,
    marketType: "pooling"
  }
]
```
{% endswagger-response %}
{% endswagger %}

### Fetch all pooling markets pertaining to a specific token and network

Return a list of **pooling markets** on a specific **network** for a specific **token**. This can be used to search for a pooling market on a specific protocol (like uniswap v3) using DAI as your asset to be put in the specific pool.

{% hint style="info" %}
Example: [https://api.decentri.fi/camelot/pooling/markets?token=0xff970a61a04b1ca14834a43f5de4533ebddb5cc8\&network=ARBITRUM](https://api.decentri.fi/camelot/pooling/markets?token=0xff970a61a04b1ca14834a43f5de4533ebddb5cc8\&network=ARBITRUM)
{% endhint %}

{% swagger method="get" path="/{protocol}/pooling/markets?token={token}&network={network}" baseUrl="https://api.defitrack.io" summary="Fetch pooling markets for a specific protocol, token and network" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="protocol" required="true" %}
slug of the protocol
{% endswagger-parameter %}

{% swagger-parameter in="query" name="token" required="true" %}
address of the token we want to find a lending market for
{% endswagger-parameter %}

{% swagger-parameter in="query" name="network" required="true" %}
network we want to find a lending market on
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
[
  {
    id: "lp_arbitrum-camelot-0xec04851c51d4478ed2827cb890b8ea87cd12e73d",
    name: "Camelot V3 KUJI/USDC",
    protocol: {
      name: "CAMELOT",
      logo: "https://github.com/defitrack/data/raw/master/logo/protocol/camelot.png",
      slug: "camelot",
      primitives: [
        "POOLING",
        "FARMING"
      ],
      website: "https://camelot.exchange//",
      company: {
        name: "Camelot",
        slug: "camelot"
      }
    },
    network: {
      name: "ARBITRUM",
      logo: "https://github.com/defitrack/data/raw/master/logo/network/arbitrum.png",
      chainId: 42161
    },
    tokens: [
      {
        address: "0x3a18dcc9745edcd1ef33ecb93b0b6eba5671e7ca",
        name: "Kujira native asset",
        decimals: 6,
        symbol: "KUJI",
        logo: "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/arbitrum/assets/0x3A18dcC9745eDcD1Ef33ecB93b0b6eBA5671e7Ca/logo.png",
        type: "SINGLE",
        totalSupply: 408705653179
      },
      {
        address: "0xff970a61a04b1ca14834a43f5de4533ebddb5cc8",
        name: "USD Coin (Arb1)",
        decimals: 6,
        symbol: "USDC",
        logo: "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/arbitrum/assets/0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8/logo.png",
        type: "SINGLE",
        totalSupply: 1068141821013203
      }
    ],
    breakdown: [],
    apr: null,
    address: "0xec04851c51d4478ed2827cb890b8ea87cd12e73d",
    decimals: 18,
    marketSize: 212.7435965974758,
    prepareInvestmentSupported: false,
    exitPositionSupported: false,
    erc20Compatible: false,
    price: 0,
    totalSupply: 0,
    metadata: {},
    updatedAt: 1688122870139,
    marketType: "pooling"
  }
]
```
{% endswagger-response %}
{% endswagger %}

###
