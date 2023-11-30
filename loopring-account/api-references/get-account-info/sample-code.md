# Sample code

### Request

```
https://uat2.loopring.io/api/v3/account?accountId=11329
```

### Response

{% code overflow="wrap" %}
```
{
	"accountId": 11329,
	"owner": "0x8656920c85342d646E5286Cb841F90209272ABeb",
	"frozen": false,
	"publicKey": {
		"x": "0x20ba7bd404f259c3d49853d6a849425a983c24fc3c01be177f719e84ba776a8c",
		"y": "0x266d7e40dba375c90816287814f20b8e187227a6d05f17d2d329fefac9b782af"
	},
	"tags": "",
	"nonce": 1,
	"keyNonce": 1,
	"keySeed": "Sign this message to access Loopring Exchange: 0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e with key nonce: 0"
}
```
{% endcode %}
