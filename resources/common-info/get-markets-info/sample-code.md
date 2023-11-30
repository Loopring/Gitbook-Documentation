# Sample code

## Request

```
https://uat2.loopring.io/api/v3/mix/markets
```

### Response

```
{
	"markets": [{
		"market": "LRC-ETH",
		"baseTokenId": 1,
		"quoteTokenId": 0,
		"precisionForPrice": 6,
		"orderbookAggLevels": 5,
		"enabled": true,
		"status": 3,
		"createdAt": "1617967800000"
	}, {
		"market": "ETH-USDT",
		"baseTokenId": 0,
		"quoteTokenId": 2,
		"precisionForPrice": 3,
		"orderbookAggLevels": 3,
		"enabled": true,
		"status": 3,
		"createdAt": "1617972300000"
	}, {
		"market": "DAI-USDT",
		"baseTokenId": 6,
		"quoteTokenId": 2,
		"precisionForPrice": 4,
		"orderbookAggLevels": 2,
		"enabled": true,
		"status": 3,
		"createdAt": "0"
	}, {
		"market": "USDC-ETH",
		"baseTokenId": 8,
		"quoteTokenId": 0,
		"precisionForPrice": 3,
		"orderbookAggLevels": 3,
		"enabled": true,
		"status": 3,
		"createdAt": "1636974420000"
	}]
}
```
