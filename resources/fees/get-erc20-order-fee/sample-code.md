# Sample code

### Header

```
X-API-KEY = bEef7a3Nzk7lgaHm85E0O1JO5ufu0iQ96p3bCmrsZz8TLGG83jTpPDYwcjUC0vlF
```



### Request

```
GET api/v3/user/orderUserRateAmount
```

```
https://uat2.loopring.io/api/v3/user/orderUserRateAmount?accountId=11329&market=lrc-eth
```



### Response

```
{
	"gasPrice": "1416666607",
	"amounts": [{
		"tokenSymbol": "LRC",
		"baseOrderInfo": {
			"minAmount": "173308254935611130661",
			"makerRate": 0,
			"takerRate": 24
		},
		"userOrderInfo": {
			"minAmount": "173308254935611130661",
			"makerRate": 0,
			"takerRate": 24
		},
		"tradeCost": "3495052197438702864"
	}, {
		"tokenSymbol": "ETH",
		"baseOrderInfo": {
			"minAmount": "2278895829392743",
			"makerRate": 0,
			"takerRate": 30
		},
		"userOrderInfo": {
			"minAmount": "2278895829392743",
			"makerRate": 0,
			"takerRate": 30
		},
		tradeCost": "12474000057750"
	}],
	"cacheOverdueAt": 1652339040
}
```
