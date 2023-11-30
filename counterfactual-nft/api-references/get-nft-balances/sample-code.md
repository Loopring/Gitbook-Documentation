---
description: Query a wallet's NFT balance for token gating
---

# Sample code

### Header

```
X-API-KEY: bEef7a3Nzk7lgaHm85E0O1JO5ufu0iQ96p3bCmrsZz8TLGG83jTpPDYwcjUC0vlF
```

### Request

{% code overflow="wrap" %}
```
https://uat2.loopring.io/api/v3/user/nft/base/balances?accountId=11329
```
{% endcode %}

### Response

{% code overflow="wrap" %}
```
{
	"totalNum": 1,
	"data": [{
		"total": 1,
		"nftData": "0x20807f0870ed096cea763ec3db94f0e4a4cffdbe0ab09187ac9972c6fd6aaecb",
	}]
}
```
{% endcode %}
