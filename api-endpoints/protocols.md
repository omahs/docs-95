# Protocols

{% swagger method="get" path="/protocols" baseUrl="https://api.defitrack.io" summary="Retrieve all protocols" %}
{% swagger-description %}
Returns all protocols (a generalization of applications, smart contracts and companies) supported by Defitrack.
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```javascript
[
   {
      "name":"AAVE",
      "logo":"https://static.defitrack.io/images/protocols/aave.png",
      "slug":"aave"
   },
   {
      "name":"HUMANDAO",
      "logo":"https://static.defitrack.io/images/protocols/humandao.jpg",
      "slug":"humandao"
   },
   {
      "name":"CURVE",
      "logo":"https://static.defitrack.io/images/protocols/curve.png",
      "slug":"curve"
   },
   {
      "name":"MSTABLE",
      "logo":"https://static.defitrack.io/images/protocols/mstable.png",
      "slug":"mstable"
   },
   {
      "name":"COMPOUND",
      "logo":"https://static.defitrack.io/images/protocols/compound.png",
      "slug":"compound"
   },
   {
      "name":"BEEFY",
      "logo":"https://static.defitrack.io/images/protocols/beefy.png",
      "slug":"beefy"
   },
   {
      "name":"QUICKSWAP",
      "logo":"https://static.defitrack.io/images/protocols/quickswap.png",
      "slug":"quickswap"
   },
   {
      "name":"POLYCAT",
      "logo":"https://static.defitrack.io/images/protocols/polycat.webp",
      "slug":"polycat"
   },
   {
      "name":"HOP",
      "logo":"https://static.defitrack.io/images/protocols/hop.jpg",
      "slug":"hop"
   },
   {
      "name":"DINOSWAP",
      "logo":"https://static.defitrack.io/images/protocols/dinoswap.png",
      "slug":"dinoswap"
   },
   {
      "name":"ADAMANT",
      "logo":"https://static.defitrack.io/images/protocols/adamant.png",
      "slug":"adamant"
   },
   {
      "name":"UNISWAP",
      "logo":"https://static.defitrack.io/images/protocols/uniswap.png",
      "slug":"uniswap"
   },
   {
      "name":"DFYN",
      "logo":"https://static.defitrack.io/images/protocols/dfyn.svg",
      "slug":"dfyn"
   },
   {
      "name":"IDEX",
      "logo":"https://static.defitrack.io/images/protocols/idex.png",
      "slug":"idex"
   },
   {
      "name":"SUSHISWAP",
      "logo":"https://static.defitrack.io/images/protocols/sushiswap.png",
      "slug":"sushiswap"
   },
   {
      "name":"DMM",
      "logo":"https://static.defitrack.io/images/protocols/dmm.png",
      "slug":"dmm"
   },
   {
      "name":"BALANCER",
      "logo":"https://static.defitrack.io/images/protocols/balancer.png",
      "slug":"balancer"
   },
   {
      "name":"CONVEX",
      "logo":"https://static.defitrack.io/images/protocols/convex.png",
      "slug":"convex"
   }
]
```
{% endswagger-response %}
{% endswagger %}
