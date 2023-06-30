# 💲 Price API

Often times, it's required to fetch the price of a token or liquidity pool. Our Price API endpoint is a microservice entirely dedicated to calculating prices, which can be used in the calculation of user holdings, market caps etc...



### Calculate a price of a holding

{% swagger method="post" path="/price" baseUrl="https://api.decentri.fi" summary="Calculate a price using the address, network and normalized amount." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="address" type="String" required="true" %}
address of the token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="network" type="Network" required="true" %}
Network the token resides on
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="BigDecimal" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="String" %}
application/json
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Value as BigDecimal" %}
```javascript
1192.9403494808796
```
{% endswagger-response %}
{% endswagger %}
