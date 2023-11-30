# Sample code

### Header

```
X-API-KEY = sptsLLthg3c9wofsdv6qykJ4mqOWFtMnGo7yKV67iA79aWWQ2fliDT42oz7764ln
```



### Request

```
GET  api/v3/user/transactions
```

```
https://uat2.loopring.io/api/v3/user/transactions?accountId=10037&limit=1
```



### Response

```
{
	"totalNum": 1482,
	"transactions": [{
		"id": 477200,
		"txType": "TRANSFER",
		"hash": "0x066241b2e57ea71f195418e94bc2b0784a2c7cff1da17d051e39f0a0aedc4dd6",
		"symbol": "LRC",
		"amount": "3523400000000000000",
		"receiver": 10855,
		"txHash": "",
		"feeTokenSymbol": "LRC",
		"feeAmount": "0",
		"status": "processed",
		"progress": "100%",
		"timestamp": 1650796057355,
		"blockNum": 0,
		"updatedAt": 1650796057423,
		"receiverAddress": "0xaa105e7fea53f040022c3e110ce9ab8ede31bc46",
		"senderAddress": "0x8737f59Cc3a96B56E94bC743b23108C30FC2624D",
		"memo": "",
		"requestId": 35955,
		"withdrawalInfo": {
			"recipient": "",
			"fastStatus": "",
			"distributeHash": ""
		},
		"blockIdInfo": {
			"blockId": 0,
			"indexInBlock": 0
		},
		"storageInfo": {
			"accountId": 10037,
			"tokenId": 1,
			"storageId": 1353
		}
	}]
}
```
