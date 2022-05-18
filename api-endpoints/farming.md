# Farming

Defitrack tries to track various farming markets across various chains. We try to maintain an up to date database of active and inactive markets in order to locate user funds, as well as locate opportunities.

Our definition of farming is any one of the following:

* Staking
* Vaults
* Liquidity Mining
* General Farming

### Farming Markets

{% swagger method="get" path="/{protocol}/staking/all-markets?network=POLYGON" baseUrl="https://api.defitrack.io" summary="Fetches all staking markets for a specific protocol on a specific network. " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="protocol" required="true" %}


slug of the protocol
{% endswagger-parameter %}

{% swagger-parameter in="query" name="network" required="true" %}
network
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Example response for Aave" %}
```javascript
[
   {
      "id":"hop-polygon-0x7bceda1db99d64f25efa279bb11ce48e15fda427",
      "network":{
         "name":"POLYGON",
         "logo":"https://static.defitrack.io/images/networks/polygon.png",
         "chainId":137
      },
      "protocol":{
         "name":"HOP",
         "logo":"https://static.defitrack.io/images/protocols/hop.jpg",
         "slug":"hop"
      },
      "name":"Hop ETH LP Token Staking Rewards",
      "stakedToken":{
         "address":"0x971039bf0a49c8d8a675f839739ee7a42511ec91",
         "name":"Hop ETH LP Token",
         "decimals":18,
         "symbol":"HOP-LP-ETH",
         "logo":null,
         "type":"HOP"
      },
      "reward":[
         {
            "address":"0x0d500b1d8e8ef31e21c99d1db9a6444d3adf1270",
            "name":"Wrapped Matic",
            "decimals":18,
            "symbol":"WMATIC",
            "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/polygon/assets/0x0d500B1d8E8eF31E21C99d1Db9A6444d3ADf1270/logo.png",
            "type":"SINGLE"
         }
      ],
      "contractAddress":"0x7bceda1db99d64f25efa279bb11ce48e15fda427",
      "vaultType":"hop-staking-rewards",
      "marketSize":0.0,
      "apr":null
   }
]
```
{% endswagger-response %}
{% endswagger %}



{% swagger method="get" path="/{protocol}/staking/markets?token={token}&network={network}" baseUrl="https://api.defitrack.io" summary="Fetch staking markets for a specific protocol, token and network" %}
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
      "id":"hop-polygon-0x7bceda1db99d64f25efa279bb11ce48e15fda427",
      "network":{
         "name":"POLYGON",
         "logo":"https://static.defitrack.io/images/networks/polygon.png",
         "chainId":137
      },
      "protocol":{
         "name":"HOP",
         "logo":"https://static.defitrack.io/images/protocols/hop.jpg",
         "slug":"hop"
      },
      "name":"Hop ETH LP Token Staking Rewards",
      "stakedToken":{
         "address":"0x971039bf0a49c8d8a675f839739ee7a42511ec91",
         "name":"Hop ETH LP Token",
         "decimals":18,
         "symbol":"HOP-LP-ETH",
         "logo":null,
         "type":"HOP"
      },
      "reward":[
         {
            "address":"0x0d500b1d8e8ef31e21c99d1db9a6444d3adf1270",
            "name":"Wrapped Matic",
            "decimals":18,
            "symbol":"WMATIC",
            "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/polygon/assets/0x0d500B1d8E8eF31E21C99d1Db9A6444d3ADf1270/logo.png",
            "type":"SINGLE"
         }
      ],
      "contractAddress":"0x7bceda1db99d64f25efa279bb11ce48e15fda427",
      "vaultType":"hop-staking-rewards",
      "marketSize":0.0,
      "apr":null
   }
]
```
{% endswagger-response %}
{% endswagger %}

