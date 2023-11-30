---
description: >-
  Allows user to create an NFT Collection with a different contract (token)
  address.
---

# Create Collection

{% hint style="info" %}
Key notes to remember:

* Metadata is required to allow user to mint NFTs to a collection
* when the collection is deployed, the NFTs will have a different contract (token) address on Layer 1.
* User can view/edit their own Collection information on Loopring L2.
* [Example of a Collection metadata](https://loopring-1.gitbook.io/loopring-university/create-your-nft/minting-nft-on-loopring/requirements-when-minting/example-with-collection-metadata)
{% endhint %}

<details>

<summary>Create Collection</summary>

{% code overflow="wrap" lineNumbers="true" %}
```ts
const eddsaKey = await signatureKeyPairMock(accInfo);
const {apiKey} = await LoopringAPI.userAPI.getUserApiKey(
 { accountId: accInfo.accountId,},
 eddsaKey.sk
);
const response = await LoopringAPI.userAPI.submitNFTCollection({
	name: 'XXX' + Date.now(), //required, one account is not able to multiple
	tileUri: 'ipfs://QmaNZ2FCgvBPqnxtkbToVVbK2Nes6xk5K4Ns6BsmkPucAM', //required
	description: 'test',
	owner: mockData.accInfo.owner,
	avatar: 'ipfs://QmaNZ2FCgvBPqnxtkbToVVbK2Nes6xk5K4Ns6BsmkPucAM',
	banner: 'ipfs://QmaNZ2FCgvBPqnxtkbToVVbK2Nes6xk5K4Ns6BsmkPucAM',
	nftFactory: NFTFactory_Collection[LOOPRING_EXPORTED_ACCOUNT.chainId as ChainId ]},
	LOOPRING_EXPORTED_ACCOUNT.chainId as ChainId,
	mockData.apiKey,
	mockData.eddsaKey.sk)
console.log('createCollection', response)
```
{% endcode %}

</details>

<details>

<summary>getUserNFTByCollection</summary>

{% code overflow="wrap" lineNumbers="true" %}
```ts
const response = await LoopringAPI.userAPI
	.getUserNFTCollection(
		{
			accountId: mockData.accInfo.accountId.toString(),
			limit: 24,
			offset: 0,
		},
		mockData.apiKey
	)
	.catch((_error) => {
		throw _error;
	});
console.log("getUserNFFByCollection", response);
```
{% endcode %}

</details>

<details>

<summary>getUserOwnCollection (User's own created collection)</summary>

{% code overflow="wrap" lineNumbers="true" %}
```ts
const response = await LoopringAPI.userAPI
  .getUserOwnCollection(
    {
      owner: mockData.accInfo.owner,
      limit: 24,
      offset: 0,
      tokenAddress: undefined,
      isMintable: false, //false
    },
    mockData.apiKey
  )
  .catch((_error) => {
    throw _error;
  });
console.log("getUserNFFByCollection", response);
```
{% endcode %}

</details>

<details>

<summary>getUserNFTCollection  (User asset NFT's Collections)</summary>

{% code overflow="wrap" lineNumbers="true" %}
```ts
const response = await LoopringAPI.userAPI
  .getUserNFTCollection({
    tokenAddress: contract, // option
    collectionId: id, // option
    accountId:  mockData.accInfo.accountId,
    limit: 20,
    offset:10,
  }, mockData.apiKey)
```
{% endcode %}

</details>

<details>

<summary>getCollectionWholeNFTs (NFTs in the Collection)</summary>

{% code overflow="wrap" lineNumbers="true" %}
```ts
 const response = await LoopringAPI.nftAPI.getCollectionWholeNFTs({
  id: 279, // collection id, it can from Market config, my NFT's -> collectionInfo, or getUserNFTCollection  
  offset: 0,
  limit: 24,
  metadata: true,
});

    
```
{% endcode %}

</details>

