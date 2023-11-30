# Sample code

### Header

```
X-API-KEY: bEef7a3Nzk7lgaHm85E0O1JO5ufu0iQ96p3bCmrsZz8TLGG83jTpPDYwcjUC0vlF
```

### Request

{% code overflow="wrap" %}
```
https://uat2.loopring.io/api/v3/user/nft/balances?accountId=11329
```
{% endcode %}

### Response

{% code overflow="wrap" %}
```
{
	"totalNum": 1,
	"data": [{
		"accountId": 11329,
		"tokenId": 32768,
		"nftData": "0x20807f0870ed096cea763ec3db94f0e4a4cffdbe0ab09187ac9972c6fd6aaecb",
		"tokenAddress": "0x486e3C172A444B3b7cB2fA91E8EBac37cb3E376C",
		"nftId": "0x8473285a59562fe413e1dfc21050214d67c479f662dd40a6ebb50d419c024fdd",
		"nftType": "ERC1155",
		"total": "10",
		"locked": "0",
		"pending": {
			"withdraw": "0",
			"deposit": "0"
		},
		"deploymentStatus": "DEPLOYED",
		"isCounterFactualNFT": true
	}]
}
```
{% endcode %}
