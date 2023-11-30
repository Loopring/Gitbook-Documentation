# Common error and solutions

Let's take api/v3/transfer for example:

## 1. ecdsaSignature:Must satisfy 0x\[0-9A-Fa-f]{132}

The signature needs to append type value(**02** or **03**):

* 02 means the signature is sign the message directly: ecdsaSign(message)
* 03 means the signature is personal\_sign in ethereum, ecdsaSign(sha256($ethereum\_header + message))

## 2. INVALID ECDSA SIGNATURE

### 2.1 check X-API-SIG

Check whether put ecdsaSignature to header is **X-API-SIG**

### 2.2 check ecdsaHash

Check whether the ecdsaHash is calculated correctly. Here is an example:

```
{
	"ecdsaHash": "0x805e1c7add987c0578fb3f67f11b05a00166706605a52ce9842a49b51f1d4302",
	"ecdsaSignature": "0x63c76604c4acd1b2a5cfd704b8780c41b9fd7ca294f5ba9e755f134f7866fb14102110f210789b17b5a1a1b218b0f85b4a439f06dbf9f9247e9c984cba6f5e381b02",
	"eddsaHash": "0x1fc4e6eedf283443892ded5e0379097dcbbbcbaefbc16a5fbbad4eaa43a4404a",
	"eddsaSignature": "0x130578bb20a310f577458bb45a06d267ac4ff4fc28ba4f9c381979b0b6c68fa917509b5fb07791147142449144d6bcb169be952a477af1f7e4044288620b3b37039a74f44cabd1bea41309e3ad2888b59771f30993be5f0aeae761fb8e013c81",
	"exchange": "0x0BABA1Ad5bE3a5C0a66E7ac838a129Bf948f1eA4",
	"maxFee": {
		"tokenId": 0,
		"volume": "13080000000000"
	},
	"memo": "",
	"payeeAddr": "0x5aab2ed473effc4ec73033725ef4b026f88f35ff",
	"payeeId": 0,
	"payerAddr": "0xc0082F333C947AAB9C1D38CcC7FbA64a32F95ECB",
	"payerId": 88886,
	"storageId": 21,
	"token": {
		"tokenId": 0,
		"volume": "1000"
	},
	"validUntil": 1652701734
}
```

Above data ecdsaHash is '0x805e1c7add987c0578fb3f67f11b05a00166706605a52ce9842a49b51f1d4302', you can use the example data to generate one ecdsaHash to compare.

### 2.3 check ecdsaPrivateKey

if 2.1 and 2.2 both are OK, check whether payerAddr is generated from ecdsaPrivateKey. You can import the ecdsaPrivateKey to MetaMask to check whether the address is the same as payerAddr.

## 3 ERR\_REST\_EDDSA\_INVALID\_SIGNATURE

### 3.1 check eddsaSignature

Check the EdDSA signature name is the same as eddsaSignature

### 3.2 check eddsaHash

Check whether the eddsaHash is calculated correctly. Here is an example:

```
{
	"ecdsaHash": "0x805e1c7add987c0578fb3f67f11b05a00166706605a52ce9842a49b51f1d4302",
	"ecdsaSignature": "0x63c76604c4acd1b2a5cfd704b8780c41b9fd7ca294f5ba9e755f134f7866fb14102110f210789b17b5a1a1b218b0f85b4a439f06dbf9f9247e9c984cba6f5e381b02",
	"eddsaHash": "0x1fc4e6eedf283443892ded5e0379097dcbbbcbaefbc16a5fbbad4eaa43a4404a",
	"eddsaSignature": "0x130578bb20a310f577458bb45a06d267ac4ff4fc28ba4f9c381979b0b6c68fa917509b5fb07791147142449144d6bcb169be952a477af1f7e4044288620b3b37039a74f44cabd1bea41309e3ad2888b59771f30993be5f0aeae761fb8e013c81",
	"exchange": "0x0BABA1Ad5bE3a5C0a66E7ac838a129Bf948f1eA4",
	"maxFee": {
		"tokenId": 0,
		"volume": "13080000000000"
	},
	"memo": "",
	"payeeAddr": "0x5aab2ed473effc4ec73033725ef4b026f88f35ff",
	"payeeId": 0,
	"payerAddr": "0xc0082F333C947AAB9C1D38CcC7FbA64a32F95ECB",
	"payerId": 88886,
	"storageId": 21,
	"token": {
		"tokenId": 0,
		"volume": "1000"
	},
	"validUntil": 1652701734
}
```

Above data ecdsaHash is '0x1fc4e6eedf283443892ded5e0379097dcbbbcbaefbc16a5fbbad4eaa43a4404a', you can use the example data to generate one eddsaHash to compare.

### 3.3 check eddsaPrivateKey format

if eddsaPrivateKey is a hex string and use java sdk to generat eddsaSignature, the eddsaKey should format be:

```
new EdDSAEngine().encode(new BigInteger(eddsaPrivateKey, 16))
```
