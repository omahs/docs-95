# 🐄 Farming Markets

Defitrack tries to track various farming markets across various chains. We try to maintain an up to date database of active and inactive markets in order to locate user funds, as well as locate opportunities.

Our definition of farming is any one of the following:

* Staking
* Vaults
* Liquidity Mining
* General Farming

### Fetching all supported markets for a specific protocol

Return a list of Farming Markets, which contain information about which tokens can be put in a vault/farm on a specific platform. It often returns the APR, which is the rate you get for providing your assets to the lending pool. Depending on the type of pool (autocompounding like Beefy Finance), the APR is the APY.&#x20;

{% swagger method="get" path="/{protocol}/staking/all-markets?network={network}" baseUrl="https://api.defitrack.io" summary="Fetches all staking markets for a specific protocol on a specific network. " %}
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

### Fetch all farming markets pertaining to a specific token and network

Return a list of Farming markets on a specific network for a specific token. This can be used to search for a lending market on a specific protocol (like Beefy Finance) using DAI as your asset to be put in the specific farm or vault.

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

### Prepare an investment transaction for a Farming Market

When [fetching farming markets](farming.md#fetching-all-supported-markets-for-a-specific-protocol), the field **prepareInvestmentSupported** is returned. This indicates whether or not Defitrack supports preparation of transactions for the underlying market. In order to  create an investment transaction to the underlying protocol, the following endpoint can be used.

![](<../.gitbook/assets/carbon (2).png>)

The result of this endpoint can be used to construct and sign transaction, without having to know the ABI. The **encoded function** and **contract address** are returned.

{% swagger method="post" path="/{protocol}/lending/markets/{id}?network={network}" baseUrl="https://api.defitrack.io" summary="Prepare investment transaction for a specificf market." %}
{% swagger-description %}
Has to be sent in JSON format. Returns a list transactions that need to be signed and submitted in order. 
{% endswagger-description %}

{% swagger-parameter in="path" name="id" required="true" type="String" %}
id of the lending market
{% endswagger-parameter %}

{% swagger-parameter in="query" name="network" required="true" %}
network we want to work on
{% endswagger-parameter %}

{% swagger-parameter in="body" name="user" type="String" required="true" %}
address of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="BigInteger" %}
can be left empty. If empty, all available balance of the required token will be used to construct the transaction.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "transactions": [
    {
      "to": "0x78AB636351c1C5f117C1442B82d14aB3a92F8464",
      "encodedFunction": "0xa0712d68000000000000000000000000000000000000000000000000000862601baa25ad"
    }
  ]
}
```
{% endswagger-response %}
{% endswagger %}

