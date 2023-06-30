---
description: >-
  Our Farming Positions module provides an easy way to get a user's position
  relative to a specific protocol. An aggregated position endpoint is not
  available due to response times.
---

# 🧑🌾 Farming Positions

## Fetch Farming Positions for a user

Return a list of all pooling positions for a specific user on a specific protocol. The result is of type Array<[FarmingPosition](../../developers/domain-model/farming/farming-position.md)>.&#x20;

If the protocol does not support Farming Markets, the result will be an empty Array.&#x20;

{% swagger method="get" path="/{protocol}/farming/{address}/positions" baseUrl="https://api.decentri.fi" summary="Get the pooling positions pertaining to a specific user for a specific protocol" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="protocol" type="string" required="true" %}
Slug of a protocol. Ex: beefy
{% endswagger-parameter %}

{% swagger-parameter in="path" name="address" type="string" required="true" %}
wallet address
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="beefy Example" %}
```javascript
[
   {
      "id":"curve-arb-2pool",
      "network":{
         "name":"ARBITRUM",
         "logo":"https://github.com/defitrack/data/raw/master/logo/network/arbitrum.png",
         "chainId":42161
      },
      "protocol":{
         "name":"BEEFY",
         "logo":"https://github.com/defitrack/data/raw/master/logo/protocol/beefy.png",
         "slug":"beefy",
         "primitives":[
            "FARMING"
         ],
         "website":"https://beefy.com"
      },
      "dollarValue":0.0,
      "name":"mooCurve2Pool Beefy Vault",
      "contractAddress":"0xEc7c0205a6f426c2Cb1667d783B5B4fD2f875434",
      "vaultType":"beefyVaultV6",
      "apr":0.0578564883820436,
      "stakedToken":{
         "address":"0x7f90122bf0700f9e7e1f688fe926940e8839f353",
         "name":"Curve.fi USDC/USDT",
         "decimals":18,
         "symbol":"2CRV",
         "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/arbitrum/assets/0x7f90122BF0700F9E7e1F688fe926940E8839F353/logo.png",
         "type":"SINGLE"
      },
      "amount":4784.774567803097,
      "underlyingAmount":4985.019824462815,
      "rewardTokens":[
         {
            "address":"0x7f90122bf0700f9e7e1f688fe926940e8839f353",
            "name":"Curve.fi USDC/USDT",
            "decimals":18,
            "symbol":"2CRV",
            "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/arbitrum/assets/0x7f90122BF0700F9E7e1F688fe926940E8839F353/logo.png",
            "type":"SINGLE"
         }
      ]
   },
   {
      "id":"polygon-bifi-maxi",
      "network":{
         "name":"POLYGON",
         "logo":"https://github.com/defitrack/data/raw/master/logo/network/polygon.png",
         "chainId":137
      },
      "protocol":{
         "name":"BEEFY",
         "logo":"https://github.com/defitrack/data/raw/master/logo/protocol/beefy.png",
         "slug":"beefy",
         "primitives":[
            "FARMING"
         ],
         "website":"https://beefy.com"
      },
      "dollarValue":31.1053447384444,
      "name":"mooPolygonBIFI Beefy Vault",
      "contractAddress":"0xfEcf784F48125ccb7d8855cdda7C5ED6b5024Cb3",
      "vaultType":"beefyVaultV6",
      "apr":0.09698379609573471,
      "stakedToken":{
         "address":"0xfbdd194376de19a88118e84e279b977f165d01b8",
         "name":"beefy.finance",
         "decimals":18,
         "symbol":"BIFI",
         "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/polygon/assets/0xFbdd194376de19a88118e84E279b977f165d01b8/logo.png",
         "type":"SINGLE"
      },
      "amount":0.06455554577859061,
      "underlyingAmount":0.07596301021827585,
      "rewardTokens":[
         {
            "address":"0xfbdd194376de19a88118e84e279b977f165d01b8",
            "name":"beefy.finance",
            "decimals":18,
            "symbol":"BIFI",
            "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/polygon/assets/0xFbdd194376de19a88118e84E279b977f165d01b8/logo.png",
            "type":"SINGLE"
         }
      ]
   },
   {
      "id":"quick-shib-matic-eol",
      "network":{
         "name":"POLYGON",
         "logo":"https://github.com/defitrack/data/raw/master/logo/network/polygon.png",
         "chainId":137
      },
      "protocol":{
         "name":"BEEFY",
         "logo":"https://github.com/defitrack/data/raw/master/logo/protocol/beefy.png",
         "slug":"beefy",
         "primitives":[
            "FARMING"
         ],
         "website":"https://beefy.com"
      },
      "dollarValue":0.14967584108022702,
      "name":"mooQuickSHIB-MATIC Beefy Vault",
      "contractAddress":"0x72B5Cf05770C9a6A99FB8652825884ee36a4BfdA",
      "vaultType":"beefyVaultV6",
      "apr":0.0,
      "stakedToken":{
         "address":"0x5fb641de2663e8a94c9dea0a539817850d996e99",
         "name":"WMATIC/SHIB LP",
         "decimals":18,
         "symbol":"WMATIC-SHIB",
         "logo":null,
         "type":"UNISWAP"
      },
      "amount":20.31692575185321,
      "underlyingAmount":24.115387043594854,
      "rewardTokens":[
         {
            "address":"0x5fb641de2663e8a94c9dea0a539817850d996e99",
            "name":"WMATIC/SHIB LP",
            "decimals":18,
            "symbol":"WMATIC-SHIB",
            "logo":null,
            "type":"UNISWAP"
         }
      ]
   },
   {
      "id":"quick-ftm-matic-eol",
      "network":{
         "name":"POLYGON",
         "logo":"https://github.com/defitrack/data/raw/master/logo/network/polygon.png",
         "chainId":137
      },
      "protocol":{
         "name":"BEEFY",
         "logo":"https://github.com/defitrack/data/raw/master/logo/protocol/beefy.png",
         "slug":"beefy",
         "primitives":[
            "FARMING"
         ],
         "website":"https://beefy.com"
      },
      "dollarValue":0.07631250343013882,
      "name":"mooQuickFTM-MATIC Beefy Vault",
      "contractAddress":"0x48e58c7E8d2063ae7ADe8a0829E00780155232eC",
      "vaultType":"beefyVaultV6",
      "apr":0.0,
      "stakedToken":{
         "address":"0xd2b61a42d3790533fedc2829951a65120624034a",
         "name":"WMATIC/FTM LP",
         "decimals":18,
         "symbol":"WMATIC-FTM",
         "logo":null,
         "type":"UNISWAP"
      },
      "amount":0.07948739943966306,
      "underlyingAmount":0.08747066723972846,
      "rewardTokens":[
         {
            "address":"0xd2b61a42d3790533fedc2829951a65120624034a",
            "name":"WMATIC/FTM LP",
            "decimals":18,
            "symbol":"WMATIC-FTM",
            "logo":null,
            "type":"UNISWAP"
         }
      ]
   }
]
```
{% endswagger-response %}
{% endswagger %}
