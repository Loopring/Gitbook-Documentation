---
description: Withdraw Loopring L2 NFT to Ethereum L1
---

# Withdraw NFT

When token is not deployed the fee is different:

\
`deployInWithdraw: tokenInfo?.deploymentStatus === DEPLOYMENT_STATUS.NOT_DEPLOYED`



<details>

<summary>Step 1: Get Account</summary>

Prepare Layer 2 account. Retrieve account information.

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

<summary>Step 4: Get storageId</summary>

Get NFT tokenId storageId

{% code overflow="wrap" lineNumbers="true" %}
```ts
const storageId = await LoopringAPI.userAPI.getNextStorageId(
  {
    accountId: accInfo.accountId,
    sellTokenId: LOOPRING_EXPORTED_ACCOUNT.nftTokenId,
  },
  apiKey
);
console.log("storageId:", storageId);

//Step 5. getUserNFTBalances
const {userNFTBalances} = await LoopringAPI.userAPI.getUserNFTBalances(
  {accountId: LOOPRING_EXPORTED_ACCOUNT.accountId},
  apiKey
);
const tokenInfo = userNFTBalances.find(
  (item) =>
    item.tokenAddress?.toLowerCase() ===
    LOOPRING_EXPORTED_ACCOUNT.nftTokenAddress.toLowerCase() &&
    item.nftId &&
    web3.utils.hexToNumberString(item.nftId) ===
    LOOPRING_EXPORTED_ACCOUNT.nftTokenId.toString()
);
```
{% endcode %}

</details>

<details>

<summary>Step 5: Withdraw fee</summary>

Get withdrawal fee.&#x20;

If the `tokenAddress` hasn't been deployed, `deployInWithdraw` set to true will retrieve the deployment fee plus withdrawal fee.&#x20;

If the `tokenAddress` is deployed, `deployInWithdraw` set to true will return withdrawal fee.

{% code overflow="wrap" lineNumbers="true" %}
```ts
const fee = await LoopringAPI.userAPI.getNFTOffchainFeeAmt(
  {
    accountId: accInfo.accountId,
    requestType: sdk.OffchainNFTFeeReqType.NFT_WITHDRAWAL,
    tokenAddress: LOOPRING_EXPORTED_ACCOUNT.nftTokenAddress,
    deployInWithdraw:
      tokenInfo?.deploymentStatus === DEPLOYMENT_STATUS.NOT_DEPLOYED, // when token is not deploy the fee is diff
  },
  apiKey
);
console.log("fee:", fee);
```
{% endcode %}

</details>

<details>

<summary>Step 6: Withdraw</summary>

{% code overflow="wrap" lineNumbers="true" %}
```ts
const response = await LoopringAPI.userAPI.submitNFTWithdraw({
  request: {
    exchange: LOOPRING_EXPORTED_ACCOUNT.exchangeAddress,
    accountId: LOOPRING_EXPORTED_ACCOUNT.accountId,
    counterFactualInfo: undefined,
    hashApproved: "",
    maxFee: {
      tokenId: TOKEN_INFO.tokenMap["LRC"].tokenId,
      amount: fee.fees["LRC"].fee ?? "9400000000000000000",
    },
    minGas: 0,
    owner: LOOPRING_EXPORTED_ACCOUNT.address,
    to: LOOPRING_EXPORTED_ACCOUNT.address,
    storageId: 0,
    token: {
      tokenId: LOOPRING_EXPORTED_ACCOUNT.nftTokenId,
      nftData: LOOPRING_EXPORTED_ACCOUNT.nftData,
      amount: "1",
    },
    validUntil: 0,
  },
  web3,
  chainId: sdk.ChainId.GOERLI,
  walletType: sdk.ConnectorNames.MetaMask,
  eddsaKey: eddsaKey.sk,
  apiKey,
});
console.log("response:", response);
```
{% endcode %}

</details>

{% hint style="success" %}
Congratulations! You have just withdrawn your NFT to Layer 1 from Loopring Layer 2!
{% endhint %}
