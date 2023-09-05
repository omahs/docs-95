---
description: >-
  We currently support a variety of events on a number of protocols and defi
  primitives. The list is subject to change.
---

# Supported Events



### Token Approval

<details>

<summary>Example</summary>

```

GET https://api.decentri.fi/events/decode/0xc39bca069cdc89832387d2dc57ef395ab2896013144a252d614e5ab2c88edb5e?network=ETHEREUM

[
  {
    "type": "APPROVAL",
    "protocol": null,
    "metadata": {
      "owner": {
        "address": "0x83a524af3cf8eb146132a2459664f7680a5515be",
        "label": null
      },
      "spender": {
        "address": "0x6b093998d36f2c7f0cc359441fbb24cc629d5ff0",
        "label": "Fulcrum DAI iToken"
      },
      "asset": {
        "network": {
          "name": "ETHEREUM",
          "logo": "https://github.com/defitrack/data/raw/master/logo/network/ethereum.png",
          "chainId": 1
        },
        "logo": "https://raw.githubusercontent.com/trustwallet/assets/master/blockchains/ethereum/assets/0x6B175474E89094C44Da98b954EedeAC495271d0F/logo.png",
        "name": "Dai Stablecoin",
        "symbol": "DAI",
        "address": "0x6b175474e89094c44da98b954eedeac495271d0f",
        "decimals": 18,
        "type": "SINGLE",
        "totalSupply": 4403467768016490697865246030,
        "underlyingTokens": [],
        "protocol": null
      },
      "amount": 115792089237316195423570985008687907853269984665640564039457584007913129639935
    }
  }
]
```

</details>

### Token Transfer

<details>

<summary>Token Transfer</summary>



</details>

### Borrow

<details>

<summary>Borrow</summary>



</details>

### Claim

<details>

<summary>Claim</summary>



</details>

### Add Liquidity

<details>

<summary>Add Liquidity</summary>



</details>

### Remove Liquidity

<details>

<summary>Remove Liquidity</summary>



</details>

### Get Reward

<details>

<summary>Get Reward</summary>



</details>

### Token Burn

<details>

<summary>Token Burn</summary>



</details>

### Swap

<details>

<summary>Swap</summary>



</details>

