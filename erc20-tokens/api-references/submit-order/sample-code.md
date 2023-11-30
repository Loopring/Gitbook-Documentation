# Sample code

### Header

```
X-API-KEY = bEef7a3Nzk7lgaHm85E0O1JO5ufu0iQ96p3bCmrsZz8TLGG83jTpPDYwcjUC0vlF
```



### Request

```
POST  api/v3/order
```

```
{
	"accountId": 10029,
	"allOrNone": false,
	"buyToken": {
		"volume": "9756234000000000000",
		"tokenId": 1
	},
	"clientOrderId": "Test",
	"eddsaSignature": "0x11751d146d388c71f6bc9258457807fc086efda3dbb83de31d70563f36d4ef0e29ade3ee80416e2ba0a67426d5797d9925336d86792fd8712496f070c551e03e0314d14117a9c611d46321b45e310cfeaa00a19b77e5aaa77c45ae630148c8bb",
	"exchange": "0xd18Ea5CE1796Be9Ce1c657E6af3FB8349a9b1927",
	"fillAmountBOrS": false,
	"hash": "0x05a97490e92ded027f65c4bebf3bad63813f4ce8c7255335894566b2eee90206",
	"maxFeeBips": 63,
	"orderType": "TAKER_ONLY",
	"poolAddress": "0x44013cbbae4a6ea70efdf6d1bb42e0dc15ab25e3",
	"sellToken": {
		"volume": "10000000",
		"tokenId": 2
	},
	"storageId": 0,
	"taker": "",
	"tradeChannel": "MIXED",
	"validUntil": 1655979919
}
```



### Response

```
{
	"hash": "0x05a97490e92ded027f65c4bebf3bad63813f4ce8c7255335894566b2eee90206",
	"clientOrderId": "Test",
	"status": "processing",
	"isIdempotent": false
}
```
