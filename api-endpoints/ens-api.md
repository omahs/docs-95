---
description: Easily fetch ENS Data based on address or name.
---

# 🔗 ENS API

ENS, short for Ethereum Name Service, is a decentralized and blockchain-based naming system designed to simplify interactions with the Ethereum ecosystem. It serves as a bridge between human-readable domain names and Ethereum addresses, making it easier for users to send and receive cryptocurrencies, interact with smart contracts, and access decentralized applications (dApps).

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

ENS replaces the need to remember long and complex Ethereum addresses with user-friendly domain names, like "myethereumwallet.eth." It functions similarly to the traditional Domain Name System (DNS) on the internet but operates on the Ethereum blockchain, providing a secure and censorship-resistant way to link names to blockchain resources.

### By Name

{% hint style="info" %}
Example: \
[https://api.decentri.fi/ens/by-name/vitalik.eth](https://api.decentri.fi/ens/by-name/vitalik.eth)
{% endhint %}

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



### By Address

{% hint style="info" %}
Example: \
[https://api.decentri.fi/ens/by-address/0xd8da6bf26964af9d7eed9e03e53415d37aa96045](https://api.decentri.fi/ens/by-address/0xd8da6bf26964af9d7eed9e03e53415d37aa96045)
{% endhint %}

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
