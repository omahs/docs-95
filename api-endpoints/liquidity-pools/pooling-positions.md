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

{% swagger method="get" path="/{protocol}/pooling/{address}/positions" baseUrl="https://api.decentri.fi" summary="Get the pooling positions pertaining to a specific user for a specific protocol" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="protocol" type="string" required="true" %}
Slug of a protocol. Ex: quickswap
{% endswagger-parameter %}

{% swagger-parameter in="path" name="address" type="string" required="true" %}
wallet address
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Quickswap Example" %}
```javascript
[
   {
      "lpAddress":"0xf04adbf75cdfc5ed26eea4bbbb991db002036bdd",
      "amount":2.1650491993E-8,
      "name":"USDC/DAI LP",
      "network":{
         "name":"POLYGON",
         "logo":"https://github.com/defitrack/data/raw/master/logo/network/polygon.png",
         "chainId":137
      },
      "symbol":"USDC-DAI",
      "protocol":{
         "name":"QUICKSWAP",
         "logo":"https://github.com/defitrack/data/raw/master/logo/protocol/quickswap.png",
         "slug":"quickswap",
         "primitives":[
            "POOLING",
            "FARMING"
         ],
         "website":"https://quickswap.exchange/"
      },
      "dollarValue":0.0,
      "id":"quickswap-polygon-0xf04adbf75cdfc5ed26eea4bbbb991db002036bdd",
      "market":{
         "id":"quickswap-polygon-0xf04adbf75cdfc5ed26eea4bbbb991db002036bdd",
         "name":"USDC/DAI LP",
         "protocol":{
            "name":"QUICKSWAP",
            "logo":"https://github.com/defitrack/data/raw/master/logo/protocol/quickswap.png",
            "slug":"quickswap",
            "primitives":[
               "POOLING",
               "FARMING"
            ],
            "website":"https://quickswap.exchange/"
         },
         "network":{
            "name":"POLYGON",
            "logo":"https://github.com/defitrack/data/raw/master/logo/network/polygon.png",
            "chainId":137
         },
         "tokens":[
            {
               "address":"0x2791bca1f2de4661ed88a30c99a7a9449aa84174",
               "name":"USD Coin (PoS)",
               "decimals":6,
               "symbol":"USDC",
               "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/polygon/assets/0x2791Bca1f2de4661ED88A30C99A7a9449Aa84174/logo.png",
               "type":"SINGLE"
            },
            {
               "address":"0x8f3cf7ad23cd3cadbd9735aff958023239c6a063",
               "name":"(PoS) Dai Stablecoin",
               "decimals":18,
               "symbol":"DAI",
               "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/polygon/assets/0x8f3Cf7ad23Cd3CaDbD9735AFf958023239c6A063/logo.png",
               "type":"SINGLE"
            }
         ],
         "apr":0.065334183322307711,
         "marketSize":7765617.196232120164971867739331142,
         "prepareInvestmentSupported":false,
         "marketType":"pooling"
      }
   },
   {
      "lpAddress":"0x019ba0325f1988213d448b3472fa1cf8d07618d7",
      "amount":0.007224506722486057,
      "name":"WMATIC/QUICK LP",
      "network":{
         "name":"POLYGON",
         "logo":"https://github.com/defitrack/data/raw/master/logo/network/polygon.png",
         "chainId":137
      },
      "symbol":"WMATIC-QUICK",
      "protocol":{
         "name":"QUICKSWAP",
         "logo":"https://github.com/defitrack/data/raw/master/logo/protocol/quickswap.png",
         "slug":"quickswap",
         "primitives":[
            "POOLING",
            "FARMING"
         ],
         "website":"https://quickswap.exchange/"
      },
      "dollarValue":0.0,
      "id":"quickswap-polygon-0x019ba0325f1988213d448b3472fa1cf8d07618d7",
      "market":{
         "id":"quickswap-polygon-0x019ba0325f1988213d448b3472fa1cf8d07618d7",
         "name":"WMATIC/QUICK LP",
         "protocol":{
            "name":"QUICKSWAP",
            "logo":"https://github.com/defitrack/data/raw/master/logo/protocol/quickswap.png",
            "slug":"quickswap",
            "primitives":[
               "POOLING",
               "FARMING"
            ],
            "website":"https://quickswap.exchange/"
         },
         "network":{
            "name":"POLYGON",
            "logo":"https://github.com/defitrack/data/raw/master/logo/network/polygon.png",
            "chainId":137
         },
         "tokens":[
            {
               "address":"0x0d500b1d8e8ef31e21c99d1db9a6444d3adf1270",
               "name":"Wrapped Matic",
               "decimals":18,
               "symbol":"WMATIC",
               "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/polygon/assets/0x0d500B1d8E8eF31E21C99d1Db9A6444d3ADf1270/logo.png",
               "type":"SINGLE"
            },
            {
               "address":"0x831753dd7087cac61ab5644b308642cc1c33dc13",
               "name":"Quickswap",
               "decimals":18,
               "symbol":"QUICK",
               "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/polygon/assets/0x831753DD7087CaC61aB5644b308642cc1c33Dc13/logo.png",
               "type":"SINGLE"
            }
         ],
         "apr":0.273568030660202589,
         "marketSize":1652366.809822224659481073260468028,
         "prepareInvestmentSupported":false,
         "marketType":"pooling"
      }
   }
]
```
{% endswagger-response %}
{% endswagger %}
