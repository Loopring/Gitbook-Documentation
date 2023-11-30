---
description: Send NFT to another account on Loopring L2
---

# Transfer NFT

<details>

<summary>Step 1: Get account Info</summary>

Prepare Loopring Layer2 account. Retrieve account information.

{% code overflow="wrap" lineNumbers="true" %}
```ts
const { exchangeInfo } = await LoopringAPI.exchangeAPI.getExchangeInfo();
const LOOPRING_EXPORTED_ACCOUNT.exchangeAddress =  exchangeInfo;
const { accInfo } = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
```
{% endcode %}

</details>

<details>

<summary>Step 2: Get eddsaKey</summary>

Generate EdDSA key

{% code overflow="wrap" lineNumbers="true" %}
```ts
const eddsaKey = await signatureKeyPairMock(accInfo);
console.log("eddsaKey:", eddsaKey.sk);
```
{% endcode %}

</details>

<details>

<summary>Step 3: Get apiKey</summary>

Retrieve the account's API key.

{% code overflow="wrap" lineNumbers="true" %}
```ts
const { apiKey } = await LoopringAPI.userAPI.getUserApiKey({
  accountId: accInfo.accountId}, eddsaKey.sk
);
console.log("apiKey:", apiKey);
const { userNFTBalances } = await LoopringAPI.userAPI.getUserNFTBalances(
  { accountId: accInfo.accountId, limit: 20 },
  apiKey
);
```
{% endcode %}

</details>

<details>

<summary>Step 4: Get storageId</summary>

Get NFT tokenId's storageId

{% code overflow="wrap" lineNumbers="true" %}
```ts
const storageId = await LoopringAPI.userAPI.getNextStorageId({
  accountId: accInfo.accountId,
  sellTokenId: LOOPRING_EXPORTED_ACCOUNT.nftTokenId,
}, apiKey);
```
{% endcode %}

</details>

<details>

<summary>Step 5: Get fee</summary>

Get transfer NFT fee

{% code overflow="wrap" lineNumbers="true" %}
```ts
const fee = await LoopringAPI.userAPI.getNFTOffchainFeeAmt({
  accountId: accInfo.accountId,
  requestType: sdk.OffchainNFTFeeReqType.NFT_TRANSFER,
  amount: "0",
}, apiKey);
console.log("fee:", fee);
```
{% endcode %}

</details>

<details>

<summary>Step 6: Transfer NFT</summary>

Transfer the NFT. Requires the EdDSA key to sign

{% code overflow="wrap" lineNumbers="true" %}
```ts
const transferResult = await LoopringAPI.userAPI.submitNFTInTransfer({
  request: {
    exchange: LOOPRING_EXPORTED_ACCOUNT.exchangeAddress,
    fromAccountId: LOOPRING_EXPORTED_ACCOUNT.accountId,
    fromAddress: LOOPRING_EXPORTED_ACCOUNT.address,
    toAccountId: 0, // toAccountId is not required, input 0 as default
    toAddress: LOOPRING_EXPORTED_ACCOUNT.address2,
    token: {
      tokenId: LOOPRING_EXPORTED_ACCOUNT.nftTokenId,
      nftData: LOOPRING_EXPORTED_ACCOUNT.nftData,
      amount: "1",
    },
    maxFee: {
      tokenId: TOKEN_INFO.tokenMap["LRC"].tokenId,
      amount: fee.fees["LRC"].fee ?? "9400000000000000000",
    },
    storageId: storageId.offchainId,
    validUntil: LOOPRING_EXPORTED_ACCOUNT.validUntil,
  },
  web3,
  chainId: sdk.ChainId.GOERLI,
  walletType: sdk.ConnectorNames.Unknown,
  eddsaKey: eddsaKey.sk,
  apiKey,
});
console.log("transfer Result:", transferResult);
```
{% endcode %}

</details>

{% hint style="success" %}
Congratulations! You have successfully transferred an NFT on Loopring Layer 2!
{% endhint %}

###



###



###

