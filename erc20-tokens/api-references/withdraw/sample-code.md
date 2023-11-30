# Sample code

### Header

```
X-API-KEY = l4hd4CGLLGuZ9nEultG4sfhQZDjPp9sv0kMy13cyGgkJyIWDodVSM4S4ucb5WFKN
X-API-SIG = 0x89cb13cd9014f222cdfae978ee7fdecba77841dc474487dfd98f08c3fc5ff8b0285a5e6e46a0a22b3839ca6d045cb9b83fa9df34b9045114b12b21b0a11149011c02
```



### Request

```
POST  api/v3/user/withdrawals
```

```
{
	"accountId": 10010,
	"eddsaSignature": "0x0d719cb234e7ed5be8c9297fda3e4efe07fc893fc039c323c830cd30da0e2c17027fd4d79840c204cd6b41b4009f1e7c338ba24281691947fabe186f8bf31b8d29cf3c1c4110405d9004fe2283379ef80216b99e45d6431521e9d7b4aa730d2c",
	"exchange": "0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e",
	"extraData": "",
	"minGas": 0,
	"maxFee": {
		"tokenId": 2,
		"volume": "15980000"
	},
	"owner": "0x6b1029c9ae8aa5eea9e045e8ba3c93d380d5bdda",
	"storageId": 1023,
	"to": "0x6b1029c9ae8aa5eea9e045e8ba3c93d380d5bdda",
	"token": {
		"tokenId": 0,
		"volume": "100000000000000"
	},
	"validUntil": 1655879582
}
```



### Response

```
{
	"hash": "0x2eabb0699ac11cf58a837a83bfd26c001c155ff7fdf9ba6f89ff96d132ce5d49",
	"status": "processing",
	"isIdempotent": false,
	"accountId": 10010,
	"tokenId": 0,
	"storageId": 1023
}
```
