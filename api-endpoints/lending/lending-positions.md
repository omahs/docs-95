---
description: >-
  Our Lending Positions module provides an easy way to get a user's position
  relative to a specific protocol. An aggregated position endpoint is not
  available due to response times.
---

# 💵 Lending Positions

## &#x20;Fetch Lending Positions for a user

Return a list of all lending positions for a specific user on a specific protocol. The result is of type Array<[LendingPosition](../../developers/domain-model/lending/lending-position.md)>.&#x20;

If the protocol does not support Lending Markets, the result will be an empty Array.&#x20;

{% swagger method="get" path="/{protocol}/lending/{address}/positions" baseUrl="https://api.decentri.fi" summary="Get the lending positions pertaining to a specific user for a specific protocol" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="protocol" type="string" required="true" %}
Slug of a protocol. Ex: compound
{% endswagger-parameter %}

{% swagger-parameter in="path" name="address" type="string" required="true" %}
wallet address
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Compound Example" %}
```javascript
[
   {
      "id":"compound-ethereum-0x4ddc2d193948926d02f9b1fe9e1daa0718270ed5",
      "network":{
         "name":"ETHEREUM",
         "logo":"https://github.com/defitrack/data/raw/master/logo/network/ethereum.png",
         "chainId":1
      },
      "protocol":{
         "name":"COMPOUND",
         "logo":"https://github.com/defitrack/data/raw/master/logo/protocol/compound.png",
         "slug":"compound",
         "primitives":[
            "LENDING",
            "BORROWING"
         ],
         "website":"https://compound.finance"
      },
      "dollarValue":1.0091431687001455E8,
      "rate":5.0E-4,
      "name":"Compound Ether",
      "amount":88628.50675770892,
      "token":{
         "address":"0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
         "name":"Wrapped Ether",
         "decimals":18,
         "symbol":"WETH",
         "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/ethereum/assets/0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2/logo.png",
         "type":"SINGLE"
      }
   },
   {
      "id":"compound-ethereum-0x35a18000230da775cac24873d00ff85bccded550",
      "network":{
         "name":"ETHEREUM",
         "logo":"https://github.com/defitrack/data/raw/master/logo/network/ethereum.png",
         "chainId":1
      },
      "protocol":{
         "name":"COMPOUND",
         "logo":"https://github.com/defitrack/data/raw/master/logo/protocol/compound.png",
         "slug":"compound",
         "primitives":[
            "LENDING",
            "BORROWING"
         ],
         "website":"https://compound.finance"
      },
      "dollarValue":2012596.031923424,
      "rate":0.0027,
      "name":"Compound Uniswap",
      "amount":374054.7281902855,
      "token":{
         "address":"0x1f9840a85d5af5bf1d1762f925bdaddc4201f984",
         "name":"Uniswap",
         "decimals":18,
         "symbol":"UNI",
         "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/ethereum/assets/0x1f9840a85d5aF5bf1D1762F925BDADdC4201F984/logo.png",
         "type":"SINGLE"
      }
   },
   {
      "id":"compound-ethereum-0x70e36f6bf80a52b3b46b3af8e106cc0ed743e8e4",
      "network":{
         "name":"ETHEREUM",
         "logo":"https://github.com/defitrack/data/raw/master/logo/network/ethereum.png",
         "chainId":1
      },
      "protocol":{
         "name":"COMPOUND",
         "logo":"https://github.com/defitrack/data/raw/master/logo/protocol/compound.png",
         "slug":"compound",
         "primitives":[
            "LENDING",
            "BORROWING"
         ],
         "website":"https://compound.finance"
      },
      "dollarValue":557202.2488553561,
      "rate":2.0E-4,
      "name":"Compound Collateral",
      "amount":13245.047998935155,
      "token":{
         "address":"0xc00e94cb662c3520282e6f5717214004a7f26888",
         "name":"Compound",
         "decimals":18,
         "symbol":"COMP",
         "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/ethereum/assets/0xc00e94Cb662C3520282E6f5717214004A7f26888/logo.png",
         "type":"SINGLE"
      }
   },
   {
      "id":"compound-ethereum-0xccf4429db6322d5c611ee964527d42e5d685dd6a",
      "network":{
         "name":"ETHEREUM",
         "logo":"https://github.com/defitrack/data/raw/master/logo/network/ethereum.png",
         "chainId":1
      },
      "protocol":{
         "name":"COMPOUND",
         "logo":"https://github.com/defitrack/data/raw/master/logo/protocol/compound.png",
         "slug":"compound",
         "primitives":[
            "LENDING",
            "BORROWING"
         ],
         "website":"https://compound.finance"
      },
      "dollarValue":3.005775536019619E8,
      "rate":4.0E-4,
      "name":"Compound Wrapped BTC",
      "amount":14436.64764069,
      "token":{
         "address":"0x2260fac5e5542a773aa44fbcfedf7c193bc2c599",
         "name":"Wrapped BTC",
         "decimals":8,
         "symbol":"WBTC",
         "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/ethereum/assets/0x2260FAC5E5542a773Aa44fBCfeDf7C193bc2C599/logo.png",
         "type":"SINGLE"
      }
   }
]
```
{% endswagger-response %}
{% endswagger %}
