---
description: >-
  We maintain an update-to-date database with labeled addresses. These addresses
  are manually checked and added to the living database.
---

# 🏷 Labeled Addresses

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### The API

{% swagger method="get" path="/{address}" baseUrl="https://api.decentri.fi/labeled-addresses" summary="Fetch a label related to an address" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="address" type="String" required="true" %}
Blockchain address
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Returns a label related to the address" %}
```json
{
   address: "0x3cc936b795a188f0e246cbb2d74c5bd190aecf18",
   tag: "Mexc.com 3"
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="Returns a 404 if no tag is related to the address" %}

{% endswagger-response %}
{% endswagger %}
