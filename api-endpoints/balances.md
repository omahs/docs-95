---
description: Balances of either native, wrapped or erc20 tokens. An API that does it all.
---

# 🪙 Balances



### Get Balance by Network



{% hint style="info" %}
Example: [https://api.decentri.fi/balance/0xf18adf71266411FF39FfC268843c9A64b3292d86/native-balance?network=POLYGON](https://api.decentri.fi/balance/0xf18adf71266411FF39FfC268843c9A64b3292d86/native-balance?network=POLYGON)
{% endhint %}



{% swagger method="get" path="/{address}/native-balance?network={network}" baseUrl="https://api.decentri.fi" summary="Fetches the native balance for an address for a specific network. Please not that using the network to filter is optional, but advised." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="address" required="true" type="String" %}
Address of the account
{% endswagger-parameter %}

{% swagger-parameter in="query" name="network" required="true" type="String" %}
network
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Example response on polygon" %}
```json
{
  "amount": 5.564687931831088,
  "network": {
    "name": "POLYGON",
    "logo": "https://github.com/defitrack/data/raw/master/logo/network/polygon.png",
    "chainId": 137
  },
  "token": {
    "address": "0x0",
    "name": "MATIC",
    "decimals": 18,
    "symbol": "MATIC",
    "logo": "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/polygon/info/logo.png",
    "type": "NATIVE",
    "totalSupply": 0
  },
  "dollarValue": 3.1209469908293266,
  "price": 0.56084852
}
```
{% endswagger-response %}
{% endswagger %}



### Get Token Balances

{% hint style="info" %}
Example: [https://api.decentri.fi/balance/0xf18adf71266411FF39FfC268843c9A64b3292d86/token-balances](https://api.decentri.fi/balance/0xf18adf71266411FF39FfC268843c9A64b3292d86/token-balances)
{% endhint %}



{% swagger method="get" path="/balance/{address}/token-balances" baseUrl="https://api.decentri.fi" summary="Fetches the token balances for an address for a specific network. Please not that using the network to filter is optional, but advised, as it fetches balances for thousands of tokens." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="address" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="query" name="network" type="String" %}
network
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Example" %}
```json
[
  {
    "amount": 10.862976703547655,
    "network": {
      "name": "OPTIMISM",
      "logo": "https://github.com/defitrack/data/raw/master/logo/network/optimism.png",
      "chainId": 10
    },
    "token": {
      "address": "0x4200000000000000000000000000000000000042",
      "name": "Optimism",
      "decimals": 18,
      "symbol": "OP",
      "logo": "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/optimism/assets/0x4200000000000000000000000000000000000042/logo.png",
      "type": "SINGLE",
      "totalSupply": 4294967295999999999998990000
    },
    "dollarValue": 14.466156098686495,
    "price": 1.331693558171961
  },
  {
    "amount": 47.336913334274065,
    "network": {
      "name": "OPTIMISM",
      "logo": "https://github.com/defitrack/data/raw/master/logo/network/optimism.png",
      "chainId": 10
    },
    "token": {
      "address": "0x9560e827af36c94d2ac33a39bce1fe78631088db",
      "name": "VelodromeV2",
      "decimals": 18,
      "symbol": "VELO",
      "logo": "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/optimism/assets/0x9560e827aF36c94D2Ac33a39bCE1Fe78631088Db/logo.png",
      "type": "SINGLE",
      "totalSupply": 1087349082336311154022319640
    },
    "dollarValue": 3.711065488308792,
    "price": 0.07839686255212194
  },
  {
    "amount": 2.516780004935962,
    "network": {
      "name": "OPTIMISM",
      "logo": "https://github.com/defitrack/data/raw/master/logo/network/optimism.png",
      "chainId": 10
    },
    "token": {
      "address": "0x1f32b1c2345538c0c6f582fcb022739c4a194ebb",
      "name": "Wrapped liquid staked Ether 2.0",
      "decimals": 18,
      "symbol": "wstETH",
      "logo": "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/optimism/assets/0x1F32b1c2345538c0c6f582fCB022739c4A194Ebb/logo.png",
      "type": "SINGLE",
      "totalSupply": 45409969073454282675352
    },
    "dollarValue": 4591.826704301722,
    "price": 1824.4847365666187
  }
]
```
{% endswagger-response %}
{% endswagger %}
