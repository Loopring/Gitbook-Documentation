---
description: Withdraw ERC20 from Loopring L2 to Ethereum L1
---

# Withdraw ERC20

Withdrawing an ERC20 token will move it from the Loopring Layer2 environment to Ethereum Layer1.

{% hint style="info" %}
Trade value should with decimals \
`sdk.toBig(value).times("1e" + TOKEN_INFO.tokenMap.LRC.decimals)`
{% endhint %}

<details>

<summary>Step 1: GetAccount</summary>

{% code lineNumbers="true" %}
```typescript
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
console.log("accInfo:", accInfo);
```
{% endcode %}

</details>

<details>

<summary>Step 2: Get eddsaKey</summary>

{% code lineNumbers="true" %}
```typescript
const eddsaKey = await signatureKeyPairMock(accInfo);
console.log("eddsaKey:", eddsaKey.sk);
```
{% endcode %}

</details>

<details>

<summary>Step 3: Get apiKey</summary>

{% code lineNumbers="true" %}
```typescript
const {apiKey} = await LoopringAPI.userAPI.getUserApiKey({
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

{% code lineNumbers="true" %}
```typescript
const storageId = await LoopringAPI.userAPI.getNextStorageId({
    accountId: accInfo.accountId,
    sellTokenId: TOKEN_INFO.tokenMap["LRC"].tokenId,
  },
  apiKey
);
console.log("storageId:", storageId);
```
{% endcode %}

</details>

<details>

<summary>Step 5: Get fee</summary>

{% code lineNumbers="true" %}
```typescript
const fee = await LoopringAPI.userAPI.getOffchainFeeAmt({
    accountId: accInfo.accountId,
    requestType: sdk.OffchainFeeReqType.OFFCHAIN_WITHDRAWAL,
    tokenSymbol: TOKEN_INFO.tokenMap["LRC"].symbol,
  },
  apiKey
);
console.log("fee:", fee);
```
{% endcode %}

</details>

<details>

<summary>Step 6: Withdraw</summary>

{% code lineNumbers="true" %}
```typescript
const response = await LoopringAPI.userAPI.submitOffchainWithdraw({
  request: {
    exchange: LOOPRING_EXPORTED_ACCOUNT.exchangeAddress,
    accountId: LOOPRING_EXPORTED_ACCOUNT.accountId,
    counterFactualInfo: undefined,
    fastWithdrawalMode: false,
    hashApproved: "",
    maxFee: {
      tokenId: TOKEN_INFO.tokenMap["LRC"].tokenId,
      volume: fee.fees["LRC"].fee ?? "9400000000000000000",
    },
    minGas: 0,
    owner: LOOPRING_EXPORTED_ACCOUNT.address,
    to: LOOPRING_EXPORTED_ACCOUNT.address,
    storageId: 0,
    token: {
      tokenId: TOKEN_INFO.tokenMap.LRC.tokenId,
      volume: LOOPRING_EXPORTED_ACCOUNT.tradeLRCValue.toString(),
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
