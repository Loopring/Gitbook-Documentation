# Sample code

### Header

{% code overflow="wrap" %}
```
X-API-KEY = l4hd4CGLLGuZ9nEultG4sfhQZDjPp9sv0kMy13cyGgkJyIWDodVSM4S4ucb5WFKN
X-API-SIG = 0xbc2e9c4f93141d2ee967abd83fd9833d99dffe26266a491e9172710e3e0162086a3624e20b5c79ca890d9827a14936606f8d5a98f21142cc1b458927483797771c02
```
{% endcode %}

### Request

```
POST  api/v3/nft/transfer
```

{% code overflow="wrap" %}
```
{
	"ecdsaSignature": "0xbc2e9c4f93141d2ee967abd83fd9833d99dffe26266a491e9172710e3e0162086a3624e20b5c79ca890d9827a14936606f8d5a98f21142cc1b458927483797771c02",
	"eddsaSignature": "0x2775ed99224c9aaf06deb484767e7fea1c224d95a16f8791ab8d83f9d3e33744299e54e7913f9250043ae53bfffe900a8c492da1f480ae148974aee7852c956626f25e7b59ab0e189b85aae0f914789af7373fae360afd04db1a61f29b14a0e2",
	"exchange": "0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e",
	"fromAccountId": 10010,
	"fromAddress": "0x6b1029c9ae8aa5eea9e045e8ba3c93d380d5bdda",
	"maxFee": {
		"tokenId": 2,
		"amount": "97700"
	},
	"memo": "test",
	"storageId": 1,
	"toAccountId": 0,
	"toAddress": "0xbB6924b24bA5c6ece81f056cF54E5d720846c183",
	"token": {
		"tokenId": 32789,
		"nftData": "0x2d4a0fc05056c1cd0e2a059b28d2072dc16cd5d083f77b48ea7d397d05e3627a",
		"amount": "1"
	},
	"validUntil": 1655874494
}
```
{% endcode %}

### Response

```
{
	"hash": "0x235c8bc8c0201013ab1a531d2d977d965b0d357ebe47e40c50ba71201c0cb86f",
	"status": "processing",
	"isIdempotent": false,
	"accountId": 10010,
	"tokenId": 0,
	"storageId": 1
}
```
