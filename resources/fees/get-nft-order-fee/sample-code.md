# Sample code

### Header

```
X-API-KEY = bEef7a3Nzk7lgaHm85E0O1JO5ufu0iQ96p3bCmrsZz8TLGG83jTpPDYwcjUC0vlF
```



### Request

```
GET api/v3/nft/info/orderUserRateAmount
```

```
https://uat2.loopring.io/api/v3/nft/info/orderUserRateAmount?accountId=11329&nftTokenAddress=0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e
```



### Response

```
{
	"nftTokenAddress": "0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e",
	"feeRate": 30,
	"amounts": [{
		"feeTokenSymbol": "ETH",
		"minAmount": "1014065144396691",
		"tradeCost": "8662500040425",
		"marketOrderInfo": {
			"minimum": "50000000000000",
			"maximum": "1000000000000000000000",
			"dust": "50000000000000"
		}
	}, {
		"feeTokenSymbol": "LRC",
		"minAmount": "151469765665366692550",
		"tradeCost": "1293907850446857443",
		"marketOrderInfo": {
			"minimum": "50000000000000000",
			"maximum": "5000000000000000000000000",
			"dust": "50000000000000000"
		}
	}, {
		"feeTokenSymbol": "USDT",
		"minAmount": "100000000",
		"tradeCost": "854236",
		"marketOrderInfo": {
			"minimum": "50000",
			"maximum": "200000000000",
			"dust": "50000"
		}
	}, {
		"feeTokenSymbol": "DAI",
		"minAmount": "100000000000000000000",
		"tradeCost": "854235064511430283",
		"marketOrderInfo": {
			"minimum": "10000000000000000000",
			"maximum": "100000000000000000000000",
			"dust": "10000000000000000000"
		}
	}],
	"gasPrice": "1500000007",
	"cacheOverdueAt": 1653128401
}
```
