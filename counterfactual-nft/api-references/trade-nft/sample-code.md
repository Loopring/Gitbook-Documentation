# Sample code

### Header

{% code overflow="wrap" %}
```
X-API-KEY = oiZ57EvM34rsHMRTjPElpZaFAt2fuKZNh6hOSELC5vRLnIvXuarRM8RuNr0apM2q
X-API-SIG = 0x087c3042fed0657680b4d589b6d90a0e67fa681466ab7fb20559aee53f668816279b53752b0e134f76eb62793968c59e56b59c70a12278129047d5f79431e2060eb5ee318aed84042cac70b70c32f1d5d906efd86171990d7af3da045013bc19
```
{% endcode %}

### Request

```
POST  api/v3/nft/trade
```

{% code overflow="wrap" %}
```
{
	"maker": {
		"exchange": "0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e",
		"accountId": 12454,
		"storageId": 54,
		"sellToken": {
			"tokenId": 32768,
			"nftData": "0x1a2001aac7a1fd00cef07889cdb67b1355f86e5bc9df71cfa44fa1c7b49f598f",
			"amount": "1"
		},
		"buyToken": {
			"tokenId": 1,
			"amount": "1000000000000000000"
		},
		"allOrNone": false,
		"fillAmountBOrS": false,
		"validUntil": 1656227891,
		"maxFeeBips": 1000,
		"eddsaSignature": "0x21f5aca209539726541d3e7165eef62c3ecfdbff6b9aa19d8793a28b08f22515258b53969cf558dfd7a221bf25082fc22f33c9b431ff6bd6847e9eb7c09de4992f6baa4ba5b5e4ee22ac7e0256c877caac31056834fc0f035bca5c230d8f532b"
	},
	"makerFeeBips": 1000,
	"taker": {
		"exchange": "0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e",
		"accountId": 10488,
		"storageId": 64,
		"sellToken": {
			"tokenId": 1,
			"amount": "1000000000000000000"
		},
		"buyToken": {
			"tokenId": 32768,
			"nftData": "0x1a2001aac7a1fd00cef07889cdb67b1355f86e5bc9df71cfa44fa1c7b49f598f",
			"amount": "1"
		},
		"allOrNone": false,
		"fillAmountBOrS": true,
		"validUntil": 1656227891,
		"maxFeeBips": 100,
		"eddsaSignature": "0x0d8606d2c3e31a3a93151954b3ba37e26188498490a0e382c0a0b5858693f3ee26e7d51a098f56320620c9cf1fe4f2790b280842a57e87b5b60abf729f61c16027e5cc88f09cf6f7fdd5c6e7eff254e6513f803059734723d60f91ba3be35a4d"
	},
	"takerFeeBips": 100
}
```
{% endcode %}

### Response

{% code overflow="wrap" %}
```
{
	"makerFills": {
		"orderHash": "0x199af4d4dcfbb7acae35d3b55a0ad99a0759f37dcef3388497e07008ec91a7d1",
		"sellFilled": {
			"tokenId": 32768,
			"nftData": "0x1a2001aac7a1fd00cef07889cdb67b1355f86e5bc9df71cfa44fa1c7b49f598f",
			"amount": "1"
		},
		"buyFilled": {
			"tokenId": 1,
			"amount": "1000000000000000000"
		},
		"fee": {
			"tokenId": 1,
			"amount": "100000000000000000"
		}
	},
	"takerFills": {
		"orderHash": "0x28b8415bd05dd7c68385e37870b6d9177cf7f8c2ba2e8ab151661114d546e799",
		"sellFilled": {
			"tokenId": 1,
			"amount": "1000000000000000000"
		},
		"buyFilled": {
			"tokenId": 32774,
			"nftData": "0x1a2001aac7a1fd00cef07889cdb67b1355f86e5bc9df71cfa44fa1c7b49f598f",
			"amount": "1"
		},
		"fee": {
			"tokenId": 1,
			"amount": "10000000000000000"
		}
	},
	"tradeHash": "0x2d4dcc071cb511cca912574aecb0076ba57e057b0716efb849b62da50926aa57",
}
```
{% endcode %}
