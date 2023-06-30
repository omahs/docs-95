# 🏊♂ Pooling Markets

Defitrack tracks various pooling markets across different chains. We try to maintain an up to date database of active and inactive markets in order to locate user funds, as well as locate opportunities.

### Fetching all supported markets for a specific protocol

Return a list of Pooling Markets, which contain information about which tokens can be put in a pool on a specific platform. It often returns the APR, which is the rate you get for providing your assets to the pool.&#x20;

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

{% swagger method="get" path="/{protocol}/pooling/markets?token={token}&network={network}" baseUrl="https://api.defitrack.io" summary="Fetch staking markets for a specific protocol, token and network" %}
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
    "id": "curve-ethereum-0x06364f10b501e868329afbc005b3492902d6c763",
    "network": "ETHEREUM",
    "protocol": "CURVE",
    "address": "0xd905e2eaebe188fc92179b6350807d8bd91db0d8",
    "name": "Curve.fi DAI/USDC/USDT/PAX",
    "symbol": "DAI/USDC/USDT/USDP",
    "tokens": [
      {
        "address": "0x6b175474e89094c44da98b954eedeac495271d0f",
        "name": "Dai Stablecoin",
        "decimals": 18,
        "symbol": "DAI",
        "logo": "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/ethereum/assets/0x6B175474E89094C44Da98b954EedeAC495271d0F/logo.png",
        "type": "SINGLE"
      },
      {
        "address": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
        "name": "USD Coin",
        "decimals": 6,
        "symbol": "USDC",
        "logo": "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/ethereum/assets/0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48/logo.png",
        "type": "SINGLE"
      },
      {
        "address": "0xdac17f958d2ee523a2206206994597c13d831ec7",
        "name": "Tether USD",
        "decimals": 6,
        "symbol": "USDT",
        "logo": "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/ethereum/assets/0xdAC17F958D2ee523a2206206994597C13D831ec7/logo.png",
        "type": "SINGLE"
      },
      {
        "address": "0x8e870d67f660d95d5be530380d0ec0bd388289e1",
        "name": "Pax Dollar",
        "decimals": 18,
        "symbol": "USDP",
        "logo": "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/ethereum/assets/0x8E870D67F660D95d5be530380D0eC0bd388289E1/logo.png",
        "type": "SINGLE"
      }
    ],
    "apr": 0.1
    "marketSize": 0,
    "tokenType": "CURVE"
  }
]
```
{% endswagger-response %}
{% endswagger %}

###
