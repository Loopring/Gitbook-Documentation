# Sample code

### Header

{% code overflow="wrap" %}
```
X-API-SIG: 0x86387c20314430db3214412eb3f252102bb2ba50df0441e263164b5202ed9ee8756268c87cc9a9216b2cbeecf17152ddc33ccbdb7500137f6f5c878ee17a81111c02
```
{% endcode %}

### Request

```
POST https://uat2.loopring.io/api/v3/account
```

{% code overflow="wrap" %}
```
{
	"accountId": 16349,
	"ecdsaSignature": "0x86387c20314430db3214412eb3f252102bb2ba50df0441e263164b5202ed9ee8756268c87cc9a9216b2cbeecf17152ddc33ccbdb7500137f6f5c878ee17a81111c02",
	"exchange": "0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e",
	"keySeed": "Sign this message to access Loopring Exchange: 0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e with key nonce: 0",
	"maxFee": {
		"tokenId": 0,
		"volume": "22700000000000"
	},
	"nonce": 0,
	"owner": "0x5a1baa04a3a799003938d4e4e7661d800913029c",
	"publicKey": {
		"x": "0x1cb92be8897bbb7537cc4f58faf31a332bac40158c76723a9c5718bf658d8dbe",
		"y": "0x0d330fbce146fbc2cc4d048e578fe2f722532809aef8c433cc4474425c6e3db7"
	},
	"validUntil": 1656166701
}
```
{% endcode %}

### Response

{% code overflow="wrap" %}
```
{
	"hash": "0x14ab2fcacb737a80af8c0b4fca7358c765df0f7163c200929c57bff27fb6a62b",
	"status": "processing",
	"isIdempotent": false,
	"accountId": 16349,
	"tokenId": 0,
	"storageId": 0
}
```
{% endcode %}
