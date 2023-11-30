---
description: mint nft in Loopring layer2, only can mint ERC1155 in layer2 now
---

# Mint NFT

## EndPoint

```
POST api/v3/nft/mint
```

## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr></tbody></table>

## Request

<table><thead><tr><th width="251.00000000000003">Query Param</th><th>Description</th><th>Example</th><th data-hidden></th><th data-hidden></th><th data-hidden></th></tr></thead><tbody><tr><td>exchange</td><td>exchangeAddress in <a href="../../../resources/common-info/get-exchange-info/">exchange info</a></td><td></td><td></td><td></td><td></td></tr><tr><td>minterAddress</td><td>minter address</td><td>"0x2aa52B5fc52c9BD3Bc7555AAB1f565f06baafF5D"</td><td></td><td></td><td></td></tr><tr><td>minterId</td><td>minter accountID</td><td>10110</td><td></td><td></td><td></td></tr><tr><td>toAddress</td><td><mark style="color:orange;">(Optional)</mark> to address</td><td></td><td></td><td></td><td></td></tr><tr><td>toAccountId</td><td>to accountId</td><td>10111，can set to 0 if dont have</td><td></td><td></td><td></td></tr><tr><td>nftType</td><td>0 for ERC1155, 1 for ERC721, now only support ERC1155</td><td>0</td><td></td><td></td><td></td></tr><tr><td>tokenAddress</td><td>tokenAddress, computed by </td><td>"0x2aa52B5fc52c9BD3Bc7555AAB1f565f06baafF5D"</td><td></td><td></td><td></td></tr><tr><td>nftId</td><td>nftId, TODO: add link</td><td>"0x3b65907396d1259f85e649531a43380aab7cfab61475f129783da7d6a6c257f1"</td><td></td><td></td><td></td></tr><tr><td>amount</td><td>how many tokens to be mint.</td><td>"1"</td><td></td><td></td><td></td></tr><tr><td>royaltyPercentage</td><td>fee to the creator of each NFT transaction. 1 ~ 10, percentage</td><td>1, means 1%</td><td></td><td></td><td></td></tr><tr><td>maxFee</td><td><a href="./#tokenamountinfo">TokenAmountInfo</a>,<br><a href="../../../resources/fees/get-nft-offchain-fee/">minter fee</a>, request type is 9</td><td></td><td></td><td></td><td></td></tr><tr><td>storageId</td><td><a href="../../../resources/storage-id/">the offchain id</a> of fee token</td><td>1</td><td></td><td></td><td></td></tr><tr><td>validUntil</td><td>Timestamp for transfer to become invalid, seconds</td><td><p></p><p>normally current time + 2 months</p></td><td></td><td></td><td></td></tr><tr><td>eddsaSignature</td><td><a href="../../../resources/signature/eddsa-signature/">eddsa signature</a><br>of the <a href="./#compute-eddsa-hash">eddsa hash</a></td><td></td><td></td><td></td><td></td></tr><tr><td>royaltyAddress</td><td><mark style="color:orange;">(Optional)</mark> fee to the address, default is minter address</td><td>"0x2aa52B5fc52c9BD3Bc7555AAB1f565f06baafF5D"</td><td></td><td></td><td></td></tr><tr><td>counterFactualInfo</td><td><a href="./#counterfactualinfo">(Optional) counterFactual Wallet Info</a></td><td>if it's counterFactual wallet, need pass the info</td><td></td><td></td><td></td></tr></tbody></table>

## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>hash</td><td>The hash identifier set by the user at the time of submission, can use this hash to get the transfer info</td><td>"0x1d923ca783<br>4dc90484fa2e<br>b611f0f0bc7e<br>741bb107007e<br>bea19ba8caea<br>b4f9d3"</td><td>string</td><td>Y</td></tr><tr><td>status</td><td>Whether the order was successfully submitted or not, please note, user may query after a while to get real process status, as most offchain requests are async processed<br>Allowable : ['received', 'processing', 'processed', 'failed']</td><td>"received"</td><td>string</td><td>Y</td></tr><tr><td>isIdempotent</td><td>Idempotent of submit transfer response, submit same transfer again idempotent will be true</td><td>"false"</td><td>boolean</td><td>Y</td></tr></tbody></table>

## Model

### **NftTokenAmountInfo**

Wrapper object used to describe a token associated with a certain quantity.

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>tokenId</td><td>The Loopring's NFT token identifier.</td><td>32769</td><td>integer</td><td>Y</td></tr><tr><td>amount</td><td><p>The amount of the NFT</p><p> token</p></td><td>"2"</td><td>string</td><td>Y</td></tr><tr><td>nftData</td><td>The Loopring's NFT token data identifier which is a hash string of NFT token address and NFT_ID</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa 8ca7100400f7c31085"</td><td></td><td></td></tr></tbody></table>

### TokenAmountInfo

ERC20 token amount info, used for fee here

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>tokenId</td><td>The Loopring's  ERC20 token identifier.</td><td>0</td><td>integer</td><td>Y</td></tr><tr><td>amount</td><td>The amount of the ERC20 token</td><td>"10000000000000000"</td><td>string</td><td>Y</td></tr></tbody></table>

### counterFactualInfo

counterFactual Wallet Info

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>walletFactory</td><td>Counter factual wallet factory contract address</td><td>"0xbbbbca6a90<br>1c926f240b89<br>eacb641d8aec<br>7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>walletOwner</td><td>Counter factual wallet owner address, NOT the wallet address</td><td>"0xbbbbca6a90<br>1c926f240b89<br>eacb641d8aec<br>7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>walletSalt</td><td>Salt to generate address from owner &#x26; other related info</td><td>"1"</td><td>string</td><td>Y</td></tr></tbody></table>



## Compute eddsa hash

```
export function getNftData(request: NFTMintRequestV3) {
  const hasher = Poseidon.createHash(7, 6, 52);
  const nftIdHi = new BN(request.nftId.substr(2, 32), 16).toString(10);
  const nftIdLo = new BN(request.nftId.substr(2 + 32, 32), 16).toString(10);
  const inputs = [
    request.minterAddress,
    request.nftType,
    request.tokenAddress,
    nftIdLo,
    nftIdHi,
    request.royaltyPercentage,
  ];
  return hasher(inputs).toString(10);
}

const inputs = [
    new BN(ethUtil.toBuffer(request.exchange)).toString(),
    request.minterId,
    request.toAccountId,
    getNftData(request),
    request.amount,
    request.maxFee.tokenId,
    request.maxFee.amount,
    request.validUntil,
    request.storageId,
  ];
  const hasher = Poseidon.createHash(inputs.length + 1, 6, 53);
  const hash = hasher(inputs).toString(10);
```

