---
description: Mint a Layer 2 NFT. Loopring follows the IPFS NFT format.
---

# Mint Counterfactual NFT

The SDK can be used to mint NFTs on Loopring's Layer 2. Minting uses IPFS and the CID will convert into the `nftId`. Review MetaNFT.md for additional details.

<details>

<summary>Step 1: Get Account</summary>

Prepare your Loopring Layer 2 account. Retrieve account information.

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

Once you have the account information, retrieve the account's EdDSA key for the minting process. Get Layer 2 EdDSA key.

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

Get fee token storageId

{% code overflow="wrap" lineNumbers="true" %}
```ts
const storageId = await LoopringAPI.userAPI.getNextStorageId(
  {
    accountId: accInfo.accountId,
    sellTokenId: LOOPRING_EXPORTED_ACCOUNT.nftTokenId, // same as maxFee tokenId
  },
  apiKey
);
```
{% endcode %}

</details>

<details>

<summary>Step 5: Get tokenAddress</summary>

Before mint user should create an collection for information with an url, follow code using the user own collection-list first item as demo&#x20;

<pre class="language-typescript" data-overflow="wrap" data-line-numbers><code class="lang-typescript"><strong>const collectionRes = await LoopringAPI.userAPI
</strong> .getUserOwenCollection({
   owner: accInfo.owner,
   isMintable: true
  },
  apiKey
 )
if ((collectionRes &#x26;&#x26;
 ((collectionRes as sdk.RESULT_INFO).code ||
  (collectionRes as sdk.RESULT_INFO).message)) || !collectionRes.collections.length
) {
 console.log("Collection is disable to mint ");
 throw "Collection is disable to mint ";
}

const collectionMeta = (collectionRes as any).collections[ 0 ] as CollectionMeta;

const counterFactualNftInfo: NFTCounterFactualInfo = {
 nftOwner: accInfo.owner,
 nftFactory: collectionMeta.nftFactory ?? sdk.NFTFactory_Collection[ sdk.ChainId.GOERLI ],
 nftBaseUri: collectionMeta.baseUri,
};
const nftTokenAddress = collectionMeta.contractAddress,
</code></pre>

</details>

<details>

<summary>Step 6: Get fee</summary>

Retrieve the mint fee.

{% code overflow="wrap" lineNumbers="true" %}
```ts
 const fee = await LoopringAPI.userAPI.getNFTOffchainFeeAmt(
  {
    accountId: accInfo.accountId,
    tokenAddress: nftTokenAddress,
    requestType: sdk.OffchainNFTFeeReqType.NFT_MINT,
  },
  apiKey
);
```
{% endcode %}

</details>

<details>

<summary>Step 7: Mint</summary>

Mint the NFT

{% code overflow="wrap" lineNumbers="true" %}
```ts
const response = await LoopringAPI.userAPI.submitNFTMint({
  request: {
    exchange: LOOPRING_EXPORTED_ACCOUNT.exchangeAddress,
    minterId: accInfo.accountId,
    minterAddress: accInfo.owner,
    toAccountId: accInfo.accountId,
    toAddress: accInfo.owner,
    nftType: 0,
    tokenAddress: nftTokenAddress,
    nftId: LOOPRING_EXPORTED_ACCOUNT.nftId, //nftId.toString(16),
    amount: "1",
    validUntil: LOOPRING_EXPORTED_ACCOUNT.validUntil,
    storageId: storageId.offchainId ?? 9,
    maxFee: {
      tokenId: TOKEN_INFO.tokenMap["LRC"].tokenId,
      amount: fee.fees["LRC"].fee ?? "9400000000000000000",
    },
    royaltyPercentage: 5,
    counterFactualNftInfo,
    forceToMint: true, // suggest use as false, for here is just for run test
  },
  web3,
  chainId: sdk.ChainId.GOERLI,
  walletType: sdk.ConnectorNames.Unknown,
  eddsaKey: eddsaKey.sk,
  apiKey: apiKey,
});
```
{% endcode %}

</details>

{% hint style="success" %}
Congratulations! You have now minted your counterfactual NFT!
{% endhint %}

###

