---
description: Various api endpoints to fetch ERC20-related token information.
---

# 🪙 ERC20



### Fetch wrapped token address

Each native token on a specific network has a wrapped version that can be used. We keep a mapping of every wrapped token version of the native token on a chain.&#x20;

{% swagger method="get" path="/erc20/{network}/wrapped" baseUrl="https://api.decentri.fi" summary="Retrieve the wrapped token of the provided network" %}
{% swagger-description %}
Retrieve the wrapped version of a network's native token. 
{% endswagger-description %}

{% swagger-parameter in="path" name="network" type="String" required="true" %}
ex: ETHEREUM
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
address: "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2"
}
```
{% endswagger-response %}
{% endswagger %}

![An example of fetching information about WETH, Ether's ERC20 equivalent on Ethereum Mainnet.](<../.gitbook/assets/carbon (4).png>)

### Fetch ERC20 Token Information

{% swagger method="get" path="/erc20/{network}/{address}/token" baseUrl="https://api.decentri.fi" summary="Fetch more information about the token. This result will indicate which type of token we're dealing with." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="network" type="String" required="true" %}
name of the network
{% endswagger-parameter %}

{% swagger-parameter in="path" name="address" type="String" required="true" %}
address of the token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Example of a single erc20 token" %}
```javascript
{
   "logo": "https://google.com",
   "name":"USD Coin",
   "symbol":"USDC",
   "address":"0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
   "decimals":6,
   "type":"SINGLE",
   "totalSupply":0,
   "underlyingTokens":[],
   "protocol":null
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Example of a Pool Token" %}
```javascript
{
  "logo": null,
  "name": "Balancer Polygon Base Pool",
  "symbol": "B-POLYBASE",
  "address": "0x0297e37f1873d2dab4487aa67cd56b58e2f27875",
  "decimals": 18,
  "type": "BALANCER",
  "totalSupply": 0,
  "underlyingTokens": [
    {
      "logo": null,
      "name": "Wrapped Matic",
      "symbol": "WMATIC",
      "address": "0x0d500b1d8e8ef31e21c99d1db9a6444d3adf1270",
      "decimals": 18,
      "type": "SINGLE",
      "totalSupply": 0,
      "underlyingTokens": [],
      "protocol": null
    },
    {
      "logo": null,
      "name": "USD Coin (PoS)",
      "symbol": "USDC",
      "address": "0x2791bca1f2de4661ed88a30c99a7a9449aa84174",
      "decimals": 6,
      "type": "SINGLE",
      "totalSupply": 0,
      "underlyingTokens": [],
      "protocol": null
    },
    {
      "logo": null,
      "name": "Wrapped Ether",
      "symbol": "WETH",
      "address": "0x7ceb23fd6bc0add59e62ac25578270cff1b9f619",
      "decimals": 18,
      "type": "SINGLE",
      "totalSupply": 0,
      "underlyingTokens": [],
      "protocol": null
    },
    {
      "logo": null,
      "name": "Balancer (PoS)",
      "symbol": "BAL",
      "address": "0x9a71012b13ca4d3d0cdc72a177df3ef03b0e76a3",
      "decimals": 18,
      "type": "SINGLE",
      "totalSupply": 0,
      "underlyingTokens": [],
      "protocol": null
    }
  ],
  "protocol": "BALANCER"
}
```
{% endswagger-response %}
{% endswagger %}

