---
description: >-
  Loopring L2 supports a method for validating one side of an NFT order. NFT
  order validation is not required for Loopring, but when making an NFT trade,
  it should pass this validation
---

# Validate NFT Order

### SellNFTByERC20

{% code overflow="wrap" lineNumbers="true" %}
```ts
// Step 1. getAccount
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
console.log("accInfo:", accInfo);

// Step 2. eddsaKey
const eddsaKey = await signatureKeyPairMock(accInfo);
console.log("eddsaKey:", eddsaKey.sk);

// Step 3. apiKey
const {apiKey} = await LoopringAPI.userAPI.getUserApiKey(
  {
    accountId: accInfo.accountId,
  },
  eddsaKey.sk
);
console.log("apiKey:", apiKey);

// Step 4. storageId
const storageId = await LoopringAPI.userAPI.getNextStorageId(
  {
    accountId: accInfo.accountId,
    sellTokenId: LOOPRING_EXPORTED_ACCOUNT.nftTokenId,
  },
  apiKey
);
console.log("storageId:", storageId);
// let hash: any = new BN(nftId,'hex')
// hash = toHex(hash);//new BigInteger(sha256(nftId.toString()).toString(), 16)

// Step 5. submitNFTValidateOrder
const response = await LoopringAPI.userAPI.submitNFTValidateOrder({
  request: {
    exchange: LOOPRING_EXPORTED_ACCOUNT.exchangeAddress,
    accountId: accInfo.accountId,
    storageId: storageId.orderId,
    sellToken: {
      tokenId: LOOPRING_EXPORTED_ACCOUNT.nftTokenId,
      nftData: LOOPRING_EXPORTED_ACCOUNT.nftData,
      amount: "1",
    },
    buyToken: {
      tokenId: 1,
      amount: "10000000000000",
    },
    allOrNone: false,
    fillAmountBOrS: false,
    validUntil: LOOPRING_EXPORTED_ACCOUNT.validUntil,
    maxFeeBips: 1000,
  },
  web3,
  chainId: sdk.ChainId.GOERLI,
  walletType: sdk.ConnectorNames.Unknown,
  eddsaKey: eddsaKey.sk,
  apiKey: apiKey,
});

console.log("sellNFT NFTOrderRequestV3:", response);
```
{% endcode %}

### BuyNFTByERC20

{% code overflow="wrap" lineNumbers="true" %}
```ts
 // Step 1. getAccount
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
console.log("accInfo:", accInfo);

// Step 2. eddsaKey
const eddsaKey = await signatureKeyPairMock(accInfo);
console.log("eddsaKey:", eddsaKey.sk);

// Step 3. apiKey
const {apiKey} = await LoopringAPI.userAPI.getUserApiKey(
  {
    accountId: accInfo.accountId,
  },
  eddsaKey.sk
);
console.log("apiKey:", apiKey);

// Step 4. submitNFTValidateOrder
const storageId = await LoopringAPI.userAPI.getNextStorageId(
  {
    accountId: accInfo.accountId,
    sellTokenId: LOOPRING_EXPORTED_ACCOUNT.nftTokenId,
  },
  apiKey
);
console.log("storageId:", storageId);

const response = await LoopringAPI.userAPI.submitNFTValidateOrder({
  request: {
    exchange: LOOPRING_EXPORTED_ACCOUNT.exchangeAddress,
    accountId: accInfo.accountId,
    storageId: storageId.orderId,
    sellToken: {
      tokenId: 1,
      amount: "10000000000000",
    },
    buyToken: {
      tokenId: LOOPRING_EXPORTED_ACCOUNT.nftTokenId,
      nftData: LOOPRING_EXPORTED_ACCOUNT.nftData,
      amount: "1",
    },
    fillAmountBOrS: true,
    allOrNone: false,
    validUntil: LOOPRING_EXPORTED_ACCOUNT.validUntil,
    maxFeeBips: 100,
  },
  web3,
  chainId: sdk.ChainId.GOERLI,
  walletType: sdk.ConnectorNames.Unknown,
  eddsaKey: eddsaKey.sk,
  apiKey: apiKey,
});
```
{% endcode %}
