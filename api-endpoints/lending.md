# Lending

Defitrack tries to track various lending markets across various chains. We try to maintain an up to date database of active and inactive markets in order to locate user funds, as well as locate opportunities.

## Lending Markets

{% swagger method="get" path="/{protocol}/lending/all-markets" baseUrl="https://api.defitrack.io" summary="Fetches all lending markets for a specific protocol. " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="protocol" required="true" %}
slug of the protocol
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Example response for Aave" %}
```javascript
[
   {
      "name":"SushiToken (PoS) Aave Pool",
      "protocol":{
         "name":"AAVE",
         "logo":"https://static.defitrack.io/images/protocols/aave.png",
         "slug":"aave"
      },
      "network":{
         "name":"POLYGON",
         "logo":"https://static.defitrack.io/images/networks/polygon.png",
         "chainId":137
      },
      "token":{
         "name":"SushiToken (PoS)",
         "symbol":"SUSHI",
         "address":"0x0b3f868e0be5597d5db7feb59e1cadbb0fdda50a",
         "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/polygon/assets/0x0b3F868E0BE5597D5DB7fEB59E1CADBb0fdDa50a/logo.png"
      },
      "rate":0.0,
      "poolType":"aave-v2",
      "marketSize":37805.98174296621
   }
]
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/{protocol}/lending/markets?token={token}&network={network}" baseUrl="https://api.defitrack.io" summary="Fetch lending markets for a specific protocol, token and network" %}
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
      "name":"USD Coin Aave Pool",
      "protocol":{
         "name":"AAVE",
         "logo":"https://static.defitrack.io/images/protocols/aave.png",
         "slug":"aave"
      },
      "network":{
         "name":"ETHEREUM",
         "logo":"https://static.defitrack.io/images/networks/ethereum.png",
         "chainId":1
      },
      "token":{
         "name":"USD Coin",
         "symbol":"USDC",
         "address":"0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
         "logo":"https://raw.githubusercontent.com/compound-finance/token-list/master/assets/asset_USDC.svg"
      },
      "rate":2.3,
      "poolType":"aave-v2",
      "marketSize":2618804765.171719
   }
]
```
{% endswagger-response %}
{% endswagger %}
