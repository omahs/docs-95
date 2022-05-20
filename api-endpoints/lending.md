# Lending

Defitrack tries to track various lending markets across various chains. We try to maintain an up to date database of active and inactive markets in order to locate user funds, as well as locate opportunities.

## Lending Markets

### Fetching all supported markets for a specific protocol

Return a list of Lending Markets, which contain information about which tokens can be lent out on a specific platform. It often returns the APR, which is the rate you get for providing your assets to the lending pool.

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
      "id":"compound-ethereum-0x6c8c6b02e7b2be14d4fa6022dfd6d75921d90e4e",
      "name":"Compound Basic Attention Token",
      "protocol":{
         "name":"COMPOUND",
         "logo":"https://static.defitrack.io/images/protocols/compound.png",
         "slug":"compound"
      },
      "network":{
         "name":"ETHEREUM",
         "logo":"https://static.defitrack.io/images/networks/ethereum.png",
         "chainId":1
      },
      "token":{
         "address":"0x0d8775f648430679a709e98d2b0cb6250d2887ef",
         "name":"Basic Attention Token",
         "decimals":18,
         "symbol":"BAT",
         "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/ethereum/assets/0x0D8775F648430679A709E98d2b0Cb6250d2887EF/logo.png",
         "type":"SINGLE"
      },
      "rate":0.0008,
      "poolType":"compound-lendingpool",
      "marketSize":54153981.17787066,
      "prepareInvestmentSupported":true
   }
]
```
{% endswagger-response %}
{% endswagger %}

### Fetch all lending markets pertaining to a specific token and network

Return a list of Lending markets on a specific network for a specific token. This can be used to search for a lending market on a specific protocol (like compound) using DAI as your asset to be lent out.

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
      "id":"compound-ethereum-0x6c8c6b02e7b2be14d4fa6022dfd6d75921d90e4e",
      "name":"Compound Basic Attention Token",
      "protocol":{
         "name":"COMPOUND",
         "logo":"https://static.defitrack.io/images/protocols/compound.png",
         "slug":"compound"
      },
      "network":{
         "name":"ETHEREUM",
         "logo":"https://static.defitrack.io/images/networks/ethereum.png",
         "chainId":1
      },
      "token":{
         "address":"0x0d8775f648430679a709e98d2b0cb6250d2887ef",
         "name":"Basic Attention Token",
         "decimals":18,
         "symbol":"BAT",
         "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/ethereum/assets/0x0D8775F648430679A709E98d2b0Cb6250d2887EF/logo.png",
         "type":"SINGLE"
      },
      "rate":0.0008,
      "poolType":"compound-lendingpool",
      "marketSize":54153981.17787066,
      "prepareInvestmentSupported":true
   }
]
```
{% endswagger-response %}
{% endswagger %}

### Prepare an investment transaction for a Lending Market

When [fetching Lending Markets](lending.md#fetching-all-supported-markets-for-a-specific-protocol), the field **prepareInvestmentSupported** is returned. This indicates whether or not Defitrack supports preparation of transactions for the underlying market. In order to  create an investment transaction to the underlying protocol, the following endpoint can be used.

The result of this endpoint can be used to construct and sign transaction, without having to know the ABI. The **encoded function** and **contract address** are returned.

{% swagger method="post" path="/{protocol}/lending/markets/{id}?network={network}" baseUrl="https://api.defitrack.io" summary="Fetch lending markets for a specific protocol, token and network" %}
{% swagger-description %}
Has to be sent in JSON format. Returns a list transactions that need to be signed and submitted in order. 
{% endswagger-description %}

{% swagger-parameter in="path" name="id" required="true" type="String" %}
id of the lending market
{% endswagger-parameter %}

{% swagger-parameter in="query" name="token" required="true" %}
address of the token we want to find a lending market for
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
      "function": {
        "name": "mint",
        "inputParameters": [
          {
            "value": 2359964734203309,
            "bitSize": 256,
            "typeAsString": "uint256"
          }
        ],
        "outputParameters": []
      },
      "encodedFunction": "0xa0712d68000000000000000000000000000000000000000000000000000862601baa25ad"
    }
  ]
}
```
{% endswagger-response %}
{% endswagger %}

