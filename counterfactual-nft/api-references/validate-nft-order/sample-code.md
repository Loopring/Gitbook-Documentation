# Sample code

### Header

{% code overflow="wrap" %}
```
X-API-KEY = oiZ57EvM34rsHMRTjPElpZaFAt2fuKZNh6hOSELC5vRLnIvXuarRM8RuNr0apM2q
```
{% endcode %}

### Request

```
POST  api/v3/nft/validateOrder
```

{% code overflow="wrap" %}
```
{
	"exchange": "0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e",
	"accountId": 12454,
	"storageId": 52,
	"sellToken": {
		"tokenId": 1,
		"amount": "10000000000000"
	},
	"buyToken": {
		"tokenId": 32768,
		"nftData": "0x1a2001aac7a1fd00cef07889cdb67b1355f86e5bc9df71cfa44fa1c7b49f598f",
		"amount": "1"
	},
	"fillAmountBOrS": true,
	"allOrNone": false,
	"validUntil": 1656169134,
	"maxFeeBips": 100,
	"eddsaSignature": "0x0199d712c7388d35cd84ab9568142e4852937c1afff3d564f39815527575f4fb0ee9db7bede135878e18421cadac15861f70eab532693cbfd6b8369f37fcd9f92da57b8000bf227b8e2a94fdb7cf27a9be71eafbacb29d7d65ce2c42f8c61dd3"
}
```
{% endcode %}

### Response

{% code overflow="wrap" %}
```
{
	"hash": "0x1c12b93ee4fc9f6bfa3784137ef145c23396c4dc921d611505b5e284cb1ba4bd",
	"status": "",
	"isIdempotent": false,
	"accountId": 12454,
	"tokens": [1],
	"storageId": 52
}
```
{% endcode %}
