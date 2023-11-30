---
description: >-
  Construct a transfer to Layer 2 broker and trigger deployment of tokenAddress
  in Layer 1
---

# Deploy NFT

<details>

<summary>Step 1: Get Account</summary>

Prepare Loopring Layer 2 account. Retrieve account information.

{% code overflow="wrap" lineNumbers="true" %}
```ts
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
console.log("accInfo:", accInfo);
```
{% endcode %}

</details>

<details>

<summary>Step 2: Get eddsaKey</summary>

Generate EdDSA key.

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
const {apiKey} = await LoopringAPI.userAPI.getUserApiKey(
  {
    accountId: accInfo.accountId,
  },
  eddsaKey.sk
);
console.log("apiKey:", apiKey);
```
{% endcode %}

</details>

<details>

<summary>Step 4: Get fee</summary>

Get deploy tokenAddress fee and set the transfer token amount.

{% code overflow="wrap" lineNumbers="true" %}
```ts
const fee = await LoopringAPI.userAPI.getNFTOffchainFeeAmt(
  {
    accountId: accInfo.accountId,
    requestType: sdk.OffchainNFTFeeReqType.NFT_DEPLOY,
    amount: "0",
  },
  apiKey
);
console.log(fee);
```
{% endcode %}

</details>

<details>

<summary>Step 5: Get storageId</summary>

Get transfer token tokenId's storageId. Using "LRC" as an example:

{% code overflow="wrap" lineNumbers="true" %}
```ts
 const storageId = await LoopringAPI.userAPI.getNextStorageId(
  {
    accountId: accInfo.accountId,
    sellTokenId: TOKEN_INFO.tokenMap["LRC"].tokenId, // same as Step 7. transfer->token->tokenId
  },
  apiKey
);
```
{% endcode %}

</details>

<details>

<summary>Step 6: Get broker</summary>

Get Loopring Layer 2 broker and set to payeeAddr of transfer

{% code overflow="wrap" lineNumbers="true" %}
```ts
const {broker} = await LoopringAPI.exchangeAPI.getAvailableBroker();
```
{% endcode %}

</details>

<details>

<summary>Step 7: Build Transfer and deploy</summary>

{% code overflow="wrap" lineNumbers="true" %}
```ts
const transfer = {
  exchange: LOOPRING_EXPORTED_ACCOUNT.exchangeAddress,
  payerAddr: LOOPRING_EXPORTED_ACCOUNT.address,
  payerId: LOOPRING_EXPORTED_ACCOUNT.accountId,
  payeeAddr: broker,
  // payeeAddr: LOOPRING_EXPORTED_ACCOUNT.address2,
  storageId: storageId.offchainId,
  token: {
    tokenId: TOKEN_INFO.tokenMap["LRC"].tokenId,
    volume: fee.fees["LRC"].fee ?? "9400000000000000000",
  },
  validUntil: LOOPRING_EXPORTED_ACCOUNT.validUntil,
};
const response = await LoopringAPI.userAPI.submitDeployNFT({
  request: {
    transfer,
    tokenAddress: LOOPRING_EXPORTED_ACCOUNT.nftTokenAddress,
    nftData: LOOPRING_EXPORTED_ACCOUNT.nftData,
  },
  web3,
  chainId: sdk.ChainId.GOERLI,
  walletType: sdk.ConnectorNames.Unknown,
  eddsaKey: eddsaKey.sk,
  apiKey: apiKey,
});

console.log(response);
```
{% endcode %}

</details>

{% hint style="success" %}
Congratulations! You have successfully deployed your Counterfactual NFT!
{% endhint %}

