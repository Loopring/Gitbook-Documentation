---
description: >-
  Each Loopring L2 transaction requires a fee to be paid (L2 transactions are
  packed, batched, and submitted to Ethereum L1 which has a gas fee).
---

# Fees

{% hint style="warning" %}
As the gasPrice changes, the fee is changed every 15 minutes.
{% endhint %}

### Pay Fee ERC20 Token : &#x20;

* Mainnet:  ETH, LRC, USDT, USDC, DAI&#x20;
* GOERLI:  ETH, LRC, USDT, DAI  &#x20;

Loopring has 2 get Fee APIs:

* getOffchainFeeAmt:
  * `ORDER`,
  * `OFFCHAIN_WITHDRAWAL`,
  * `UPDATE_ACCOUNT`,
  * `TRANSFER`,
  * `FAST_OFFCHAIN_WITHDRAWAL`,
  * `OPEN_ACCOUNT`,
  * `AMM_EXIT`,
  * `DEPOSIT`,
  * `AMM_JOIN`,
* getNFTOffchainFeeAmt:
  * `NFT_MINT`,
  * `NFT_WITHDRAWAL`,
  * `NFT_TRANSFER`,
  * `NFT_DEPLOY`,

### Fee: updateAccount

```ts
    // Step 1. get account info
console.log(LoopringAPI.exchangeAPI.getAccount);

const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
console.log("accInfo:", accInfo);

// Step 2. eddsaKey
const eddsaKey = await signatureKeyPairMock(accInfo);
console.log("eddsaKey:", eddsaKey.sk);

// Step 3. get apikey
const {apiKey} = await LoopringAPI.userAPI.getUserApiKey(
  {
    accountId: accInfo.accountId,
  },
  eddsaKey.sk
);
console.log("apiKey:", apiKey);
return {accInfo, eddsaKey, apiKey};

const response = await LoopringAPI.userAPI.getOffchainFeeAmt(
  {
    accountId: accInfo.accountId,
    requestType: sdk.OffchainFeeReqType.UPDATE_ACCOUNT,
  },
  apiKey
);
console.log("updateAccount:", response);
```



### Fee: transfer

```ts
    // Step 1. get account info
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
console.log("accInfo:", accInfo);

// Step 2. eddsaKey
const eddsaKey = await signatureKeyPairMock(accInfo);
console.log("eddsaKey:", eddsaKey.sk);

// Step 3. get apikey
const {apiKey} = await LoopringAPI.userAPI.getUserApiKey(
  {
    accountId: accInfo.accountId,
  },
  eddsaKey.sk
);
console.log("apiKey:", apiKey);
return {accInfo, eddsaKey, apiKey};
const response = await LoopringAPI.userAPI.getOffchainFeeAmt(
  {
    accountId: accInfo.accountId,
    requestType: sdk.OffchainFeeReqType.TRANSFER,
  },
  apiKey
);
console.log("transfer:", response);
```

### Fee: withdraw

```ts
    // Step 1. get account info
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
console.log("accInfo:", accInfo);

// Step 2. eddsaKey
const eddsaKey = await signatureKeyPairMock(accInfo);
console.log("eddsaKey:", eddsaKey.sk);

// Step 3. get apikey
const {apiKey} = await LoopringAPI.userAPI.getUserApiKey(
  {
    accountId: accInfo.accountId,
  },
  eddsaKey.sk
);
console.log("apiKey:", apiKey);
return {accInfo, eddsaKey, apiKey};
const response = await LoopringAPI.userAPI.getOffchainFeeAmt(
  {
    accountId: accInfo.accountId,
    tokenSymbol: TOKEN_INFO.tokenMap.LRC.symbol,
    requestType: sdk.OffchainFeeReqType.OFFCHAIN_WITHDRAWAL,
  },
  apiKey
);
console.log("withdraw:", response);
```



### Fee: fastWithdraw

```ts
    // Step 1. get account info
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
console.log("accInfo:", accInfo);

// Step 2. eddsaKey
const eddsaKey = await signatureKeyPairMock(accInfo);
console.log("eddsaKey:", eddsaKey.sk);

// Step 3. get apikey
const {apiKey} = await LoopringAPI.userAPI.getUserApiKey(
  {
    accountId: accInfo.accountId,
  },
  eddsaKey.sk
);
console.log("apiKey:", apiKey);
return {accInfo, eddsaKey, apiKey};
const response = await LoopringAPI.userAPI.getOffchainFeeAmt(
  {
    accountId: accInfo.accountId,
    requestType: sdk.OffchainFeeReqType.FAST_OFFCHAIN_WITHDRAWAL,
    tokenSymbol: TOKEN_INFO.tokenMap.LRC.symbol,
  },
  apiKey
);
console.log("fastWithdraw:", response);
```



### Fee: order

```ts
    // Step 1. get account info
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
console.log("accInfo:", accInfo);

// Step 2. eddsaKey
const eddsaKey = await signatureKeyPairMock(accInfo);
console.log("eddsaKey:", eddsaKey.sk);

// Step 3. get apikey
const {apiKey} = await LoopringAPI.userAPI.getUserApiKey(
  {
    accountId: accInfo.accountId,
  },
  eddsaKey.sk
);
console.log("apiKey:", apiKey);
return {accInfo, eddsaKey, apiKey};
const response = await LoopringAPI.userAPI.getOffchainFeeAmt(
  {
    accountId: accInfo.accountId,
    requestType: sdk.OffchainFeeReqType.ORDER,
    tokenSymbol: TOKEN_INFO.tokenMap.LRC.symbol,
  },
  apiKey
);
console.log("order:", response);
```

### Fee: amm\_exit

```ts
    // Step 1. get account info
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
console.log("accInfo:", accInfo);

// Step 2. eddsaKey
const eddsaKey = await signatureKeyPairMock(accInfo);
console.log("eddsaKey:", eddsaKey.sk);

// Step 3. get apikey
const {apiKey} = await LoopringAPI.userAPI.getUserApiKey(
  {
    accountId: accInfo.accountId,
  },
  eddsaKey.sk
);
console.log("apiKey:", apiKey);
return {accInfo, eddsaKey, apiKey};
const response = await LoopringAPI.userAPI.getOffchainFeeAmt(
  {
    accountId: accInfo.accountId,
    requestType: sdk.OffchainFeeReqType.AMM_EXIT,
  },
  apiKey
);
console.log("amm_exit:", response);
```

### Fee: amm\_join

```ts
    // Step 1. get account info
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
console.log("accInfo:", accInfo);

// Step 2. eddsaKey
const eddsaKey = await signatureKeyPairMock(accInfo);
console.log("eddsaKey:", eddsaKey.sk);

// Step 3. get apikey
const {apiKey} = await LoopringAPI.userAPI.getUserApiKey(
  {
    accountId: accInfo.accountId,
  },
  eddsaKey.sk
);
console.log("apiKey:", apiKey);
return {accInfo, eddsaKey, apiKey};
const response = await LoopringAPI.userAPI.getOffchainFeeAmt(
  {
    accountId: accInfo.accountId,
    requestType: sdk.OffchainFeeReqType.AMM_JOIN,
  },
  apiKey
);
console.log("amm_join:", response);
```

### Fee: NFTTransfer

```ts
    // Step 1. get account info
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
console.log("accInfo:", accInfo);

// Step 2. eddsaKey
const eddsaKey = await signatureKeyPairMock(accInfo);
console.log("eddsaKey:", eddsaKey.sk);

// Step 3. get apikey
const {apiKey} = await LoopringAPI.userAPI.getUserApiKey(
  {
    accountId: accInfo.accountId,
  },
  eddsaKey.sk
);
console.log("apiKey:", apiKey);
return {accInfo, eddsaKey, apiKey};
const response = await LoopringAPI.userAPI.getNFTOffchainFeeAmt(
  {
    accountId: accInfo.accountId,
    requestType: sdk.OffchainNFTFeeReqType.NFT_TRANSFER,
  },
  apiKey
);
console.log("NFTTransfer:", response);
```

### Fee: NFTWithdrawal

```ts
    // Step 1. get account info
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
console.log("accInfo:", accInfo);

// Step 2. eddsaKey
const eddsaKey = await signatureKeyPairMock(accInfo);
console.log("eddsaKey:", eddsaKey.sk);

// Step 3. get apikey
const {apiKey} = await LoopringAPI.userAPI.getUserApiKey(
  {
    accountId: accInfo.accountId,
  },
  eddsaKey.sk
);
console.log("apiKey:", apiKey);
return {accInfo, eddsaKey, apiKey};
const response = await LoopringAPI.userAPI.getNFTOffchainFeeAmt(
  {
    accountId: accInfo.accountId,
    tokenAddress: LOOPRING_EXPORTED_ACCOUNT.nftTokenAddress,
    requestType: sdk.OffchainNFTFeeReqType.NFT_WITHDRAWAL,
  },
  apiKey
);
console.log("NFTWithdrawal:", response);
```

### getActiveFeeInfo without apikey & accountId

```ts
const response = await LoopringAPI.globalAPI.getActiveFeeInfo({});
```

### getActiveFeeInfo without apikey with accountId

```ts
const response = await LoopringAPI.globalAPI.getActiveFeeInfo({ accountId: LOOPRING_EXPORTED_ACCOUNT.accountId });
```
