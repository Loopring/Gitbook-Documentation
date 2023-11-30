# Signature and verification

The Loopring wallet is a **smart contract wallet**. Its address is a contract wallet address.  There is an owner who controls the wallet.&#x20;

The wallet signature is signed by the owner, and the contract records the owner. Although the signature is actually signed by the owner you cannot get the owner, so you need to verify the signature through the wallet contract.



Loopring also has a **counterfactual wallet**, which means the wallet's contract hasn't been deployed. To deploy the contract, you need to get the actual owner from the Loopring server.

You can verify the signature one by one (use contract wallet verification and counterfactual wallet verification), if one of the two passes the signature is verified.

{% hint style="info" %}
The signature is a little different from EOA wallets, and it can also be verified by the wallet contract.
{% endhint %}

We append **02** or **03** after the signature, for example, the signature is: 0x05b49f99ac6d8f67d4519dfaf9b545dbc775dcc837441f85ef9aae74c83e5c2d700729cdba1d7a9cc818abb43a598cf1e4eeca547e4e6697ff18c4d2ac111ac21b02

* 02 means the signature is sign the message directly: ecdsaSign(message)
* 03 means the signature is like personal\_sign in ethereum, ecdsaSign(sha256($ethereum\_header + message))

### Contract Wallet

There is a need to call the contract (wallet address) to verify the signature is EIP1271 standard:

```
https://eips.ethereum.org/EIPS/eip-1271
```

The verify flow:

```
1. encode the call data use:
			encodeInputs(
      "isValidSignature(bytes32,bytes)",
      {
        _data: hash,
        _signature: toBuffer(sig),
      }
  hash is the message, sig is the signature

2. If the return value is 0x1626ba7e, means verify success, else the signature is not correct or the wallet is locked can not use now.
```



### Counterfactual Wallet

1. Use the address to get owner info

#### Endpoint

(goerli is uat2.loopring.io, mainnet is api3.loopring.io):

```
https://uat2.loopring.io/api/v3/counterFactualInfo?address=0xf8989b0d3f5e2ee877dca8897748772a4ce83888
```

#### Response:

```
{
	"accountId": 12413,
	"wallet": "0xf8989b0d3f5e2ee877dca8897748772a4ce83888",
	"walletFactory": "0x8c3d4e1728f77abcd220323260da4a9306fb6433",
	"walletSalt": "1648381750",
	"walletOwner": "0xd9702ea86111c6efe0d3ae2851f994696527a9a4"
}
```

1. So the signature is signed by the walletOwner. you can use ecrecover to verify the signature:
   * if the signature ends with 02: the recover message is the message
   * if the signature ends with 03: the recover message is sha256($ethereum\_header + message)

### [JS example](../signature/sdk-signature/)

### Test Env: Goerli

Android apk:&#x20;
