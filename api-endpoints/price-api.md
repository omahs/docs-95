# 💲 Price API

Often times, it's required to fetch the price of a token or liquidity pool. Our Price API endpoint is a microservice entirely dedicated to calculating prices, which can be used in the calculation of user holdings, market caps etc...



{% swagger method="get" path="/price/{symbol}" baseUrl="https://api.defitrack.io" summary="Fetch the price for a token symbol. Result is a BigDecimal." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="symbol" type="String" required="true" %}
Symbol of the token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Value of the token" %}
```javascript
1192.9403494808796
```
{% endswagger-response %}
{% endswagger %}
