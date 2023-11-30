---
description: Deposit NFTs (ERC1155 and ERC721) from Ethereum Layer 1 to Loopring Layer 2
---

# Deposit NFT

{% hint style="warning" %}
All Deposit Methods: Users should have enough `ETH` to pay for the Ethereum Gas fee (Loopring does not charge a fee for Deposit).
{% endhint %}

<details>

<summary>Step 1: getNFTBalance &#x26; getEthBalances</summary>

Get Layer 1 NFT balance and ETH balance

{% code overflow="wrap" lineNumbers="true" %}
```ts
const {ethBalance} = await LoopringAPI.exchangeAPI.getEthBalances({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
const nftBalance = await LoopringAPI.nftAPI.getNFTBalance({
  web3,
  account: LOOPRING_EXPORTED_ACCOUNT.address,
  tokenAddress: LOOPRING_EXPORTED_ACCOUNT.nftTokenAddress,
  nftId: LOOPRING_EXPORTED_ACCOUNT.nftId,
  nftType: sdk.NFTType.ERC1155,
});
```
{% endcode %}

</details>

<details>

<summary>Step 2: isApprovedForAll</summary>

Check NFT token is approved by the Loopring exchange address

{% code overflow="wrap" lineNumbers="true" %}
```ts
 const isApprovedForAll = await LoopringAPI.nftAPI.isApprovedForAll({
  web3,
  from: LOOPRING_EXPORTED_ACCOUNT.address,
  exchangeAddress: LOOPRING_EXPORTED_ACCOUNT.exchangeAddress,
  nftType: sdk.NFTType.ERC1155, // todo： sdk.NFTType.ERC721
  tokenAddress: LOOPRING_EXPORTED_ACCOUNT.nftTokenAddress,
});
console.log(`check is approveNFT`, isApprovedForAll);
```
{% endcode %}

</details>

<details>

<summary>Step 3: approveNFT All</summary>

Approve NFT to Loopring exchange address

{% code overflow="wrap" lineNumbers="true" %}
```ts
  if (!isApprovedForAll) {
  const nonce = await sdk.getNonce(
    web3,
    LOOPRING_EXPORTED_ACCOUNT.address
  );
  const approveNFT = await LoopringAPI.nftAPI.approveNFT({
    web3,
    from: LOOPRING_EXPORTED_ACCOUNT.address,
    depositAddress: LOOPRING_EXPORTED_ACCOUNT.depositAddress,
    tokenAddress: LOOPRING_EXPORTED_ACCOUNT.nftTokenAddress,
    nftType: sdk.NFTType.ERC1155, // todo： sdk.NFTType.ERC721
    gasPrice: LOOPRING_EXPORTED_ACCOUNT.gasPrice,
    gasLimit: LOOPRING_EXPORTED_ACCOUNT.gasLimit,
    chainId: sdk.ChainId.GOERLI,
    nonce,
    sendByMetaMask: true,
  });
  console.log(`nonce: ${nonce} approveNFT: ${approveNFT?.result}`);
}
```
{% endcode %}

</details>

<details>

<summary>Step 4: nonce</summary>

We will need to retrieve a Layer1 nonce in order to perform the deposit. Use the `getNonce` function to retrieve this for an address. Get Layer 1 nonce

{% code overflow="wrap" lineNumbers="true" %}
```ts
 const nonce = await sdk.getNonce(web3, LOOPRING_EXPORTED_ACCOUNT.address);

console.log(
  `deposit: NFT, gasPrice: ${LOOPRING_EXPORTED_ACCOUNT.gasPrice}, `
);
```
{% endcode %}

</details>

<details>

<summary>Step 5: depositNFT</summary>

Deposit NFT to the Loopring exchange

{% code overflow="wrap" lineNumbers="true" %}
```ts
  const response = await LoopringAPI.nftAPI.depositNFT({
  web3,
  from: LOOPRING_EXPORTED_ACCOUNT.address,
  exchangeAddress: LOOPRING_EXPORTED_ACCOUNT.exchangeAddress,
  nftType: sdk.NFTType.ERC1155,   // todo： sdk.NFTType.ERC721
  tokenAddress: LOOPRING_EXPORTED_ACCOUNT.nftTokenAddress,
  nftId: LOOPRING_EXPORTED_ACCOUNT.nftId,
  amount: 2,   // todo：when sdk.NFTType.ERC721  amount: 1,
  gasPrice: LOOPRING_EXPORTED_ACCOUNT.gasPrice,
  gasLimit: LOOPRING_EXPORTED_ACCOUNT.gasLimit + 100000,
  chainId: sdk.ChainId.GOERLI,
  nonce,
  sendByMetaMask: true,
});
console.log(`nonce: ${nonce} deposit NFT ERC1155: `, response);
```
{% endcode %}

</details>

{% hint style="success" %}
Congratulations! You have successfully your Layer 1 NFT to Loopring Layer 2!
{% endhint %}
