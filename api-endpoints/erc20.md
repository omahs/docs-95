---
description: Various api endpoints to fetch ERC20-related token information.
---

# ERC20

### Fetch wrapped token address

{% swagger method="get" path="/erc20/{network}/wrapped" baseUrl="https://api.defitrack.io" summary="Retrieve the wrapped token of the provided network" %}
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

{% swagger method="get" path="/erc20/{network}/{address}/token" baseUrl="https://api.defitrack.io" summary="Fetch more information about the token. This result will indicate which type of token we're dealing with." %}
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

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}
