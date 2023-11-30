# Sample code

### Header

```
X-API-KEY = bEef7a3Nzk7lgaHm85E0O1JO5ufu0iQ96p3bCmrsZz8TLGG83jTpPDYwcjUC0vlF
```



### Request

```
GET api/v3/user/nft/offchainFee
```

```
https://uat2.loopring.io/api/v3/user/nft/offchainFee?accountId=11329&requestType=10
```



### Response

```
{
	"gasPrice": "1500000008",
	"fees": [{
			"token": "ETH",
			"fee": "217000000000000",
			"discount": 1
		},
		{
			"token": "LRC",
			"fee": "1248000000000000000",
			"discount": 1
		},
		{
			"token": "USDT",
			"fee": "1550000",
			"discount": 1
		},
		{
			"token": "DAI",
			"fee": "1550000000000000000",
			"discount": 1
		}
	]
}
```
