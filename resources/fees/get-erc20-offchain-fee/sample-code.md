# Sample code

### Header

```
X-API-KEY = bEef7a3Nzk7lgaHm85E0O1JO5ufu0iQ96p3bCmrsZz8TLGG83jTpPDYwcjUC0vlF
```



### Request

```
GET api/v3/user/offchainFee
```

```
https://uat2.loopring.io/api/v3/user/offchainFee?accountId=11329&requestType=2
```



### Response

```
{
	"gasPrice": "1500000008",
	"fees": [{
			"token": "ETH",
			"fee": "26400000000000",
			"discount": 1
		},
		{
			"token": "LRC",
			"fee": "121500000000000000",
			"discount": 0.8
		},
		{
			"token": "USDT",
			"fee": "150900",
			"discount": 0.8
		},
		{
			"token": "DAI",
			"fee": "188600000000000000",
			"discount": 1
		}
	]
}
```
