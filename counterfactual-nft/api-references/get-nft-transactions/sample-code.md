# Sample code

### Header

```
X-API-KEY = bEef7a3Nzk7lgaHm85E0O1JO5ufu0iQ96p3bCmrsZz8TLGG83jTpPDYwcjUC0vlF
```

### Request

```
GET  api/v3/user/nft/transactions

https://uat2.loopring.io/api/v3/user/nft/transactions?accountId=10010
```

### Response

```
{
	"totalNum": 1,
	"transactions": [{
		"id": 22649,
		"requestId": 6799,
		"hash": "0x0b3fff000a2bfd5de4334eb9cd25e747ca85faca87e2f27e37ebb0ce426d656d",
		"txHash": "",
		"nftTxType": "MINT",
		"nftData": "0x2b25a42050405ea97575cdcac558a25b4e6c3e1f16b03fd1ce3c413a289aa5fa",
		"amount": "11",
		"feeTokenSymbol": "USDT",
		"feeAmount": "1557000",
		"status": "processed",
		"timestamp": 1649045073989,
		"updatedAt": 1649045074261,
		"memo": "",
		"receiverAddress": "",
		"senderAddress": "0x6b1029c9ae8aa5eea9e045e8ba3c93d380d5bdda",
		"receiver": 0,
		"storageInfo": {
			"accountId": 10010,
			"tokenId": 32785,
			"storageId": 1039
		},
		"withdrawalInfo": {
			"recipient": "",
			"fastStatus": "false",
			"distributeHash": ""
		},
		"minterInfo": {
			"accountId": 10010,
			"minter": "0x6b1029c9ae8aa5eea9e045e8ba3c93d380d5bdda",
			"originalMinter": ""
		},
		"nftStatusInfo": {
			"deploymentStatus": "NOT_DEPLOYED",
			"isCounterFactualNFT": true,
			"nftType": "ERC1155",
			"tokenAddress": "0xC30E4cB0853470E6a412Ca7f21363cD0D26428e8",
			"tokenId": "0x3726262992c8b58b67404984a3199c6ba1ed5b8440a29b0410a25c940ff25ffe"
		}
	}]
}
```
