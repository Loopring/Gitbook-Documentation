# Sample code

### Header

{% code overflow="wrap" %}
```
X-API-KEY = iN0O39N33E76EAPUbApaMhKrngwtYRr0y7tvSG6HBvT3Yb5vNN4luroeffpz7UxQ
X-API-SIG = 0x14ce9cfe92d46432d3bb303cd4d8a923e174ff67f92bbd19cc21f06e0729330e07c1cfad338bd951d9f4024589c14cf8403e1e72cc6185fb8f8a3b2b25dac7b30c43ee2a4076772be6c7c85e5617a36ec6f160b5051d4af4f823848c0ca6809a
```
{% endcode %}

### Request

```
POST  api/v3/nft/deployTokenAddress
```

{% code overflow="wrap" %}
```
{
	"nftData": "0x079f309296a1d8932424cb681ccbfb6c9641e6b1c31ab75a5790d4700e4bebda",
	"tokenAddress": "0xf7001d035e68e4dc4e1f713ab67d1278f9fbe47c",
	"transfer": {
		"exchange": "0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e",
		"payerAddr": "0x44DDED4865F2640ccC5a5D8F0923ce6E68Aac381",
		"payerId": 11649,
		"payeeAddr": "0xa3961aAE9522f0F66f2406aC6FaA2aF0A8BFe504",
		"storageId": 3,
		"token": {
			"tokenId": 2,
			"volume": "14340000"
		},
		"validUntil": 1655882076,
		"payeeId": 0,
		"memo": "NFT-DEPLOY-CONTRACT->0xf7001d035e68e4dc4e1f713ab67d1278f9fbe47c",
		"maxFee": {
			"volume": "0",
			"tokenId": 2
		},
		"eddsaSignature": "0x10913dbe5b95948591cb6b522e228bfc499319ff60edf91ffa13783f39e126a71aefaf98e09e98e625eba88ff1ee7ec7c8b27ee194309a62e7d76273a5cce19b0952ef4d556b602281f6c7b2483231eec7e2b8cb366cf584c31e61e1659bb784",
		"ecdsaSignature": "0xbba6a20260318ec8682d4d0f166e16d32f164aa6419a71671ce026e51523d1b34461d43fa7ae268831ad6e3c653b1e633e6fb85fe2769696d425bff6aeaf03491c02"
	}
}
```
{% endcode %}

### Response

```
{
	"hash": "0xf2a58ff716454e22d80292717188e12d15d4d2ae888cfe29dc033a364d1124c3",
	"status": "SEND_TX_SUCCESS",
	"isIdempotent": false,
	"accountId": 11649,
	"tokenId": 2,
	"storageId": 3
}
```
