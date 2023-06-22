---
description: API support for ENS naming
---

# 🔗 ENS

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### The API

{% swagger method="get" path="/by-name/{ens-name}" baseUrl="https://api.decentri.fi/ens" summary="Fetch an address by ENS name" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="ens-name" type="String" required="true" %}
ENS Name of a user
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
  "name": "vitalik.eth",
  "address": "0xd8da6bf26964af9d7eed9e03e53415d37aa96045"
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/by-address/{address}" baseUrl="https://api.decentri.fi/ens" summary="Fetch an ENS name by address" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="address" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```
{
   "name": "vitalik.eth",
   "address": "0xd8da6bf26964af9d7eed9e03e53415d37aa96045"
}
```
{% endswagger-response %}
{% endswagger %}
