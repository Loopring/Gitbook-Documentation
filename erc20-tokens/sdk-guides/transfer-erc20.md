---
description: Send ERC20 tokens to another account on Loopring L2
---

# Transfer ERC20

The SDK provides the ability to transfer a supported ERC20 token to another account on Loopring Layer2.

{% hint style="info" %}
Trade value should with decimals&#x20;

`sdk.toBig(value).times("1e" + TOKEN_INFO.tokenMap.LRC.decimals)`
{% endhint %}

```typescript
const { exchangeInfo } = await LoopringAPI.exchangeAPI.getExchangeInfo();
const LOOPRING_EXPORTED_ACCOUNT.exchangeAddress =  exchangeInfo;
```

<details>

<summary>Step 1: Get account Info</summary>

{% code overflow="wrap" lineNumbers="true" %}
```typescript
const { accInfo } = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
console.log("accInfo:", accInfo);p
```
{% endcode %}

</details>

<details>

<summary>Step 2: Get eddsaKey</summary>

<pre class="language-typescript" data-line-numbers><code class="lang-typescript"><strong>const eddsaKey = await signatureKeyPairMock(accInfo);
</strong>console.log("eddsaKey:", eddsaKey.sk);
</code></pre>

</details>

<details>

<summary>Step 3: Get apikey</summary>

{% code lineNumbers="true" %}
```typescript
const { apiKey } = await LoopringAPI.userAPI.getUserApiKey(
  {
    accountId: accInfo.accountId,
  },
  eddsaKey.sk
);
console.log("apiKey:", apiKey);
const { userBalances } = await LoopringAPI.userAPI.getUserBalances(
  { accountId: LOOPRING_EXPORTED_ACCOUNT.accountId, tokens: "" },
  apiKey
);
```
{% endcode %}

</details>

<details>

<summary>Step 4: Get storageId</summary>

{% code overflow="wrap" lineNumbers="true" %}
```typescript
const storageId = await LoopringAPI.userAPI.getNextStorageId(
  {
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

{% code overflow="wrap" lineNumbers="true" %}
```typescript
const fee = await LoopringAPI.userAPI.getOffchainFeeAmt({
  accountId: accInfo.accountId,
  requestType: sdk.OffchainFeeReqType.TRANSFER,
}, apiKey);
console.log("fee:", fee);
```
{% endcode %}

</details>

<details>

<summary>Step 6: Transfer</summary>

{% code lineNumbers="true" %}
```typescript
const transferResult = await LoopringAPI.userAPI.submitInternalTransfer({
  request: {
    exchange: LOOPRING_EXPORTED_ACCOUNT.exchangeAddress,
    payerAddr: accInfo.owner,
    payerId: accInfo.accountId,
    payeeAddr: LOOPRING_EXPORTED_ACCOUNT.address2,
    payeeId: LOOPRING_EXPORTED_ACCOUNT.accountId2,
    storageId: storageId.offchainId,
    token: {
      tokenId: TOKEN_INFO.tokenMap.LRC.tokenId,
      volume: LOOPRING_EXPORTED_ACCOUNT.tradeLRCValue.toString(),
    },
    maxFee: {
      tokenId: TOKEN_INFO.tokenMap["LRC"].tokenId,
      volume: fee.fees["LRC"].fee ?? "9400000000000000000",
    },
    validUntil: LOOPRING_EXPORTED_ACCOUNT.validUntil,
  },
  web3,
  chainId: sdk.ChainId.GOERLI,
  walletType: sdk.ConnectorNames.Trezor,
  eddsaKey: eddsaKey.sk,
  apiKey: apiKey,
});
console.log("transferResult:", transferResult);
```
{% endcode %}

</details>
