# Sample code

### Header

```
X-API-KEY = l4hd4CGLLGuZ9nEultG4sfhQZDjPp9sv0kMy13cyGgkJyIWDodVSM4S4ucb5WFKN
X-API-SIG = 0x33f9a4fa0c439067e90dcbfc2a0522fee7a18f511c9956824fb2760bba15eb8a349fe76bd7acbf3c7bc165834767f282844b1a680d81cb5b35a45bd7fa8a91c11b02
```



### Request

```
POST  api/v3/transfer
```

```
{
	"eddsaSignature": "0x210238285d9855c97fb581876021ef3315506c997b79a409256d791d0883bc622e3a441537b893ac6d09e1e5b01f163d72e3ab6c04fad50e66416f23eac8d0f12122818e943171229b7b130b732e39113b71e41be79b4d644b5d76d2208fb749",
	"exchange": "0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e",
	"maxFee": {
		"tokenId": 2,
		"volume": "97700"
	},
	"memo": "test",
	"payeeAddr": "0x44DDED4865F2640ccC5a5D8F0923ce6E68Aac381",
	"payeeId": 0,
	"payerAddr": "0x6b1029c9ae8aa5eea9e045e8ba3c93d380d5bdda",
	"payerId": 10010,
	"storageId": 1021,
	"token": {
		"tokenId": 0,
		"volume": "100000000000000"
	},
	"validUntil": 1655879465
}
```



### Response

```
{
	"hash": "0x0cd6d70917ce6cf9c9b13a11d14aa3381285c1ab018d357ba043ed08c4bdb672",
	"status": "processing",
	"isIdempotent": false,
	"accountId": 10010,
	"tokenId": 0,
	"storageId": 1021
}
```
