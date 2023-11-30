# Sample code

### Header

{% code overflow="wrap" %}
```
X-API-KEY = l4hd4CGLLGuZ9nEultG4sfhQZDjPp9sv0kMy13cyGgkJyIWDodVSM4S4ucb5WFKN
X-API-SIG = 0x6c5a6278358b80a4e1ea4aafabe798723b501576457203c92b8c84bd0e426ea67083a79ae7bb07d99f56cffc102d514ebad4397ff13ea9a7660369ca994a8de21b02
```
{% endcode %}

### Request

```
POST  api/v3/nft/mint
```

{% code overflow="wrap" %}
```
{
	"amount": "12",
	"ecdsaSignature": "0x6c5a6278358b80a4e1ea4aafabe798723b501576457203c92b8c84bd0e426ea67083a79ae7bb07d99f56cffc102d514ebad4397ff13ea9a7660369ca994a8de21b02",
	"eddsaSignature": "0x1e6a1876c82b7887d6713f4af73c2c663df350c0356b1aba63bc007342e371f50012082ae7cefa9c0402c41ac66445e6f66d10f6f68c6a85891d55c55d23e2ea1132034085593d5b8b057c2ba6f814b0cc5654baeec8d871e0625d05785cc030",
	"exchange": "0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e",
	"forceToMint": false,
	"maxFee": {
		"tokenId": 2,
		"amount": "21400000"
	},
	"minterAddress": "0x6b1029c9ae8aa5eea9e045e8ba3c93d380d5bdda",
	"minterId": 10010,
	"nftId": "0x407294a8f36d3bdc4d04a6fce57afe0f8d49da56e04db83eb146c39ca24102e1",
	"nftType": 0,
	"royaltyPercentage": 0,
	"storageId": 1059,
	"toAccountId": 10010,
	"toAddress": "0x6b1029c9ae8aa5eea9e045e8ba3c93d380d5bdda",
	"tokenAddress": "0xc30e4cb0853470e6a412ca7f21363cd0d26428e8",
	"validUntil": 1655873983
}
```
{% endcode %}

### Response

{% code overflow="wrap" %}
```
{
	"hash": "0x019242e2b67e16862d0191ca9a5013599f33856b91f47aed8025d44fb85ed946",
	"nftTokenId": 32789,
	"nftData": "0x2d4a0fc05056c1cd0e2a059b28d2072dc16cd5d083f77b48ea7d397d05e3627a",
	"status": "processing",
	"isIdempotent": false,
	"accountId": 10010,
	"storageId": 1059
}
```
{% endcode %}
