---
description: >-
  Our Invest module allows you to integrate calling protocol contracts
  seamlessly without knowing the underlying domain model.
---

# 🦺 Invest

### Prepare an investment / Enter a market

Preparing an investment will create prepared transactions. If the protocol and underlying farm/lending pool/liquidity pool support it, one or more transactions will be prepared. Often times, the first transaction is an approval transaction.&#x20;

{% swagger method="post" path="/{protocol}/{markettype}/markets/{marketId}/enter" baseUrl="https://api.decentri.fi" summary="Prepare an investment. Returns a list of prepared transactions that need to be signed. " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="markettype" type="string" required="true" %}
one of [farming, lending, pooling]
{% endswagger-parameter %}

{% swagger-parameter in="path" name="marketId" type="string" required="true" %}
id of the underlying market
{% endswagger-parameter %}

{% swagger-parameter in="path" name="protocol" type="string" required="true" %}
slug of a protocol
{% endswagger-parameter %}

{% swagger-parameter in="body" name="user" type="string" required="true" %}
address wanting to enter the market
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="BigInteger" required="true" %}
amount to be entered the market into
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Example of Aave Enter Response" %}
```javascript
{
  "transactions": [
    {
      "function": {
        "name": "approve",
        "inputParameters": [
          {
            "value": "0x8dff5e27ea6b7ac08ebfdf9eb090f32ee9a30fcf",
            "typeAsString": "address"
          },
          {
            "value": 18446744073709551615,
            "bitSize": 256,
            "typeAsString": "uint256"
          }
        ],
        "outputParameters": []
      },
      "to": "0x2791bca1f2de4661ed88a30c99a7a9449aa84174",
      "data": "0x095ea7b30000000000000000000000008dff5e27ea6b7ac08ebfdf9eb090f32ee9a30fcf000000000000000000000000000000000000000000000000ffffffffffffffff"
    }
  ]
}
```
{% endswagger-response %}
{% endswagger %}
