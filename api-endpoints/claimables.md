---
description: >-
  Find out whether an account has claimables waiting around. Claimables are any
  kind of on-chain actions an account can perform with positive outcome.
  Examples of this are yield that can be claimed.
---

# 💰 Claimables

### Claimable Building Block



{% swagger method="get" path="/{address}" baseUrl="https://claimables.decentri.fi" summary="Get Claimables for a specific address." %}
{% swagger-description %}
This call gets all possible claimables for an address.
{% endswagger-description %}

{% swagger-parameter in="path" name="address" type="String" required="true" %}
address of the user
{% endswagger-parameter %}

{% swagger-parameter in="query" name="include" type="Array<String>" %}
what protocols to include
{% endswagger-parameter %}

{% swagger-parameter in="query" name="exclude" type="Array<String>" %}
what protocols to exclude
{% endswagger-parameter %}
{% endswagger %}

## The Native API

Did you know you can also use the native API to get Claimables for specific protocols?&#x20;

{% swagger method="get" path="/{protocol}/{address}/claimables" baseUrl="https://api.decentri.fi" summary="Fetch claimables pertaining to specific account for a protocol. " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="protocol" type="String" required="true" %}
slug of the protocol
{% endswagger-parameter %}

{% swagger-parameter in="path" name="address" type="String" required="true" %}
address of the account
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}


```json
[
  {
    "id": "3f71a866-1a4f-4a97-99cf-5aa670a8cacc",
    "name": "WETH/OP LP Gauge V2 reward",
    "type": "velodrome-reward",
    "protocol": {
      "name": "VELODROME_V2",
      "logo": "https://github.com/defitrack/data/raw/master/logo/protocol/velodrome.svg",
      "slug": "velodrome_v2",
      "primitives": [
        "POOLING",
        "FARMING"
      ],
      "website": "https://app.velodrome.finance",
      "company": {
        "name": "Velodrome",
        "slug": "velodrome"
      }
    },
    "network": {
      "name": "OPTIMISM",
      "logo": "https://github.com/defitrack/data/raw/master/logo/network/optimism.png",
      "chainId": 10
    },
    "dollarValue": 19.929648647161816,
    "amount": 254.2148754219806,
    "token": {
      "address": "0x9560e827af36c94d2ac33a39bce1fe78631088db",
      "name": "VelodromeV2",
      "decimals": 18,
      "symbol": "VELO",
      "logo": "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/optimism/assets/0x9560e827aF36c94D2Ac33a39bCE1Fe78631088Db/logo.png",
      "type": "SINGLE",
      "totalSupply": 296514877005303546555804032
    },
    "claimTransaction": {
      "network": {
        "name": "OPTIMISM",
        "logo": "https://github.com/defitrack/data/raw/master/logo/network/optimism.png",
        "chainId": 10
      },
      "function": {
        "name": "getReward",
        "inputParameters": [
          {
            "value": "0xf18adf71266411ff39ffc268843c9a64b3292d86",
            "typeAsString": "address"
          }
        ],
        "outputParameters": []
      },
      "to": "0xcc53cd0a8ec812d46f0e2c7cc5aadd869b6f0292",
      "from": null,
      "data": "0xc00007b0000000000000000000000000f18adf71266411ff39ffc268843c9a64b3292d86"
    }
  },
  {
    "id": "76271ad2-99b3-454c-84f7-55db64019ef7",
    "name": "WETH/rETH LP Gauge V2 reward",
    "type": "velodrome-reward",
    "protocol": {
      "name": "VELODROME_V2",
      "logo": "https://github.com/defitrack/data/raw/master/logo/protocol/velodrome.svg",
      "slug": "velodrome_v2",
      "primitives": [
        "POOLING",
        "FARMING"
      ],
      "website": "https://app.velodrome.finance",
      "company": {
        "name": "Velodrome",
        "slug": "velodrome"
      }
    },
    "network": {
      "name": "OPTIMISM",
      "logo": "https://github.com/defitrack/data/raw/master/logo/network/optimism.png",
      "chainId": 10
    },
    "dollarValue": 0.5422478286164714,
    "amount": 6.916703181277941,
    "token": {
      "address": "0x9560e827af36c94d2ac33a39bce1fe78631088db",
      "name": "VelodromeV2",
      "decimals": 18,
      "symbol": "VELO",
      "logo": "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/optimism/assets/0x9560e827aF36c94D2Ac33a39bCE1Fe78631088Db/logo.png",
      "type": "SINGLE",
      "totalSupply": 296514877005303546555804032
    },
    "claimTransaction": {
      "network": {
        "name": "OPTIMISM",
        "logo": "https://github.com/defitrack/data/raw/master/logo/network/optimism.png",
        "chainId": 10
      },
      "function": {
        "name": "getReward",
        "inputParameters": [
          {
            "value": "0xf18adf71266411ff39ffc268843c9a64b3292d86",
            "typeAsString": "address"
          }
        ],
        "outputParameters": []
      },
      "to": "0xd0e434831a765839051da9c0b9b99c6b0fb87201",
      "from": null,
      "data": "0xc00007b0000000000000000000000000f18adf71266411ff39ffc268843c9a64b3292d86"
    }
  }
]
```
{% endswagger-response %}
{% endswagger %}
