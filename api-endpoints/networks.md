---
description: >-
  Decentrifi currently supports 6 different (EVM compatible) networks. In order
  to get all the networks it supports, you can use the following endpoints.
---

# 📶 Networks

{% swagger method="get" path="/networks" baseUrl="https://api.decentri.fi" summary="Fetch all available networks on the platform. " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```javascript
[
   {
      "name":"ETHEREUM",
      "logo":"https://static.defitrack.io/images/networks/ethereum.png",
      "slug":"ethereum"
   },
   {
      "name":"OPTIMISM",
      "logo":"https://static.defitrack.io/images/networks/optimism.png",
      "slug":"optimism"
   },
   {
      "name":"ARBITRUM",
      "logo":"https://static.defitrack.io/images/networks/arbitrum.png",
      "slug":"arbitrum"
   },
   {
      "name":"FANTOM",
      "logo":"https://static.defitrack.io/images/networks/fantom.png",
      "slug":"fantom"
   },
   {
      "name":"AVALANCHE",
      "logo":"https://static.defitrack.io/images/networks/avalanche.png",
      "slug":"avalanchex"
   },
   {
      "name":"BSC",
      "logo":"https://static.defitrack.io/images/networks/bsc.svg",
      "slug":"smartchain"
   },
   {
      "name":"POLYGON",
      "logo":"https://static.defitrack.io/images/networks/polygon.png",
      "slug":"polygon"
   },
   {
      "name":"POLYGON_MUMBAI",
      "logo":"https://static.defitrack.io/images/networks/polygon.png",
      "slug":"polygon_mumbai"
   }
]
```
{% endswagger-response %}
{% endswagger %}
