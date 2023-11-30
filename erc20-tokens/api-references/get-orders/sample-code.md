# Sample code

### Header

```
X-API-KEY = sptsLLthg3c9wofsdv6qykJ4mqOWFtMnGo7yKV67iA79aWWQ2fliDT42oz7764ln
```



### Request

```
GET  api/v3/orders
```

```
https://uat2.loopring.io/api/v3/orders?accountId=10010&limit=10&status=processed%2Cfailed%2Ccancelled%2Ccancelling%2Cexpired
```



### Response

```
{
	"totalNum": 8,
	"orders": [{
		"hash": "0x019eb52193352b40ec11fb17185a38e2e551d1ccd3b7b2f4590b87c6eb010873",
		"clientOrderId": "0x019eb52193352b40ec11fb17185a38e2e551d1ccd3b7b2f4590b87c6eb010873",
		"side": "BUY",
		"market": "ETH-USDT",
		"price": "103422.027",
		"volumes": {
			"baseAmount": "1073272330970261",
			"quoteAmount": "111000000",
			"baseFilled": "1080880000000000",
			"quoteFilled": "111000000",
			"fee": "1080880000000"
		},
		"validity": {
			"start": 1655106079,
			"end": 1657698077
		},
		"orderType": "TAKER_ONLY",
		"tradeChannel": "MIXED",
		"status": "processed",
		"storageInfo": {
			"accountId": 10010,
			"tokenId": 2,
			"storageId": 1028
		}
	}]
}
```
