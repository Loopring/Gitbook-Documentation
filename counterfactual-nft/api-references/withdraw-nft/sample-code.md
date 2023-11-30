# Sample code

### Header

```
X-API-KEY = l4hd4CGLLGuZ9nEultG4sfhQZDjPp9sv0kMy13cyGgkJyIWDodVSM4S4ucb5WFKN
X-API-SIG = 0x8a9ed00eaf47deec677760a477c907746f9f40c53bf1e8b3b75a81e34b2911806817d9856fb987fba0a363b472db7a359dd54296e55befcf4f24605a138203e81b02
```

### Request

```
POST  api/v3/nft/withdrawal
```

```
{
	"accountId": 10010,
	"ecdsaSignature": "0x8a9ed00eaf47deec677760a477c907746f9f40c53bf1e8b3b75a81e34b2911806817d9856fb987fba0a363b472db7a359dd54296e55befcf4f24605a138203e81b02",
	"eddsaSignature": "0x03120f328edbb2e40bfb47eb86a11697d796acfc364ba6617d62d060378c1cf4128f905bd8206e6420a9392806dd6df655489017d3d8ce9622c06e4b960447c41c1993f6c9f6c9a2a9a82c55b3e23c376db670c6a09e01fa4338bc3de3bc1065",
	"exchange": "0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e",
	"extraData": "",
	"maxFee": {
		"tokenId": 2,
		"amount": "34200000"
	},
	"minGas": 0,
	"owner": "0x6b1029c9ae8aa5eea9e045e8ba3c93d380d5bdda",
	"storageId": 3,
	"to": "0xbB6924b24bA5c6ece81f056cF54E5d720846c183",
	"token": {
		"tokenId": 32789,
		"nftData": "0x2d4a0fc05056c1cd0e2a059b28d2072dc16cd5d083f77b48ea7d397d05e3627a",
		"amount": "2"
	},
	"validUntil": 1655874620
}
```

### Response

```
{
	"hash": "0x0c7fbf3eb9e3c154b34083def8f32b9467c0fa1e06ba2d5e683c4fc19edc93ef",
	"status": "processing",
	"isIdempotent": false,
	"accountId": 10010,
	"tokenId": 0,
	"storageId": 3
}
```
