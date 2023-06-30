---
description: >-
  Transactions contain events. Often, these aren't easily decoded and require
  domain knowledge. We deliver endpoints to decode publicly known events.
---

# 👩💻 Event Decoders



{% hint style="info" %}
Example: [https://api.decentri.fi/events/decode/0xc39bca069cdc89832387d2dc57ef395ab2896013144a252d614e5ab2c88edb5e?network=ETHEREUM](https://api.decentri.fi/events/decode/0xc39bca069cdc89832387d2dc57ef395ab2896013144a252d614e5ab2c88edb5e?network=ETHEREUM)
{% endhint %}

{% swagger method="get" path="/{transactionHash}?network={NETWORK}" baseUrl="https://api.decentri.fi/events/decode" summary="Fetch all events that decentrifi can decode from a given transaction on a network." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="transactionHash" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="query" name="NETWORK" required="true" %}
Network, like "ETHEREUM"
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="All events in this transaction" %}
```json
[
   {
      "type":"APPROVAL",
      "protocol":null,
      "metadata":{
         "owner":"0x83a524af3cf8eb146132a2459664f7680a5515be",
         "spender":"0x6b093998d36f2c7f0cc359441fbb24cc629d5ff0",
         "asset":{
            "network":{
               "name":"ETHEREUM",
               "logo":"https://github.com/defitrack/data/raw/master/logo/network/ethereum.png",
               "chainId":1
            },
            "logo":"https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/ethereum/assets/0x6B175474E89094C44Da98b954EedeAC495271d0F/logo.png",
            "name":"Dai Stablecoin",
            "symbol":"DAI",
            "address":"0x6b175474e89094c44da98b954eedeac495271d0f",
            "decimals":18,
            "type":"SINGLE",
            "totalSupply":4.8457660702839423e+27,
            "underlyingTokens":[
               
            ],
            "protocol":null
         },
         "amount":1.157920892373162e+77
      }
   }
]
```
{% endswagger-response %}
{% endswagger %}
