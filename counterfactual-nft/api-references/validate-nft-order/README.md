---
description: validate a NFT order
---

# Validate NFT Order

## EndPoint

```
POST api/v3/nft/validateOrder
```

## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr></tbody></table>

## Request

<table><thead><tr><th width="248.00000000000003">Query Param</th><th>Description</th><th>Example</th><th data-hidden></th><th data-hidden></th><th data-hidden></th></tr></thead><tbody><tr><td>exchange</td><td>exchangeAddress in <a href="../../../resources/common-info/get-exchange-info/">exchange info</a></td><td></td><td></td><td></td><td></td></tr><tr><td>accountId</td><td>accountId</td><td>10110</td><td></td><td></td><td></td></tr><tr><td>storageId</td><td><a href="../../../resources/storage-id/">storageId</a> of sell tokenId in</td><td>2</td><td></td><td></td><td></td></tr><tr><td>sellToken</td><td><a href="./#nfttokenamountinfo">NftTokenAmountInfo</a>, NFT token if sell NFT order else erc20 token like USDT</td><td></td><td></td><td></td><td></td></tr><tr><td>buyToken</td><td><a href="./#nfttokenamountinfo">NftTokenAmountInfo</a>, NFT token if buy NFT order else erc20 token like USDT</td><td></td><td></td><td></td><td></td></tr><tr><td>validUntil</td><td>Timestamp for transfer to become invalid, seconds</td><td><p></p><p>normally current time + 2 months</p></td><td></td><td></td><td></td></tr><tr><td>maxFeeBips</td><td>Maximum order fee that the user can accept, value range (in ten thousandths) 1 ~ 5000</td><td>100, means 1%</td><td></td><td></td><td></td></tr><tr><td>eddsaSignature</td><td><a href="../../../resources/signature/eddsa-signature/">eddsa signature</a><br>of the <a href="./#compute-eddsa-hash"> eddsa hash</a></td><td></td><td></td><td></td><td></td></tr><tr><td>clientOrderId</td><td><mark style="color:orange;">(Optional)</mark> An arbitrary, client-set unique order identifier, max length is 120 bytes</td><td>"test"</td><td></td><td></td><td></td></tr><tr><td>affiliate</td><td><mark style="color:orange;">(Optional)</mark> An accountID who will receive a share of the fee of this order at the end of monthly distribution.<br>Need contact us to add the accountId in whitelist.</td><td>10110</td><td></td><td></td><td></td></tr></tbody></table>

## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>hash</td><td>The hash identifier set by the user at the time of submission, can use this hash to get the transfer info</td><td>"0x1d923ca7834dc90484fa2eb611f0f0bc7e741bb107007ebea19ba8caeab4f9d3"</td><td>string</td><td>Y</td></tr><tr><td>status</td><td>Whether the order was successfully submitted or not, please note, user may query after a while to get real process status, as most offchain requests are async processed<br>Allowable : ['received', 'processing', 'processed', 'failed']</td><td>"received"</td><td>string</td><td>Y</td></tr><tr><td>isIdempotent</td><td>Idempotent of submit transfer response, submit same transfer again idempotent will be true</td><td>false</td><td>boolean</td><td>Y</td></tr></tbody></table>

##

## Model

### **NftTokenAmountInfo**

Wrapper object used to describe a token associated with a certain quantity.

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>tokenId</td><td>The Loopring's NFT token identifier.</td><td>32769</td><td>integer</td><td>Y</td></tr><tr><td>amount</td><td><p>The amount of the NFT</p><p> token</p></td><td>"2"</td><td>string</td><td>Y</td></tr><tr><td>nftData</td><td>The Loopring's NFT token data identifier which is a hash string of NFT token address and NFT_ID</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa 8ca7100400f7c31085"</td><td></td><td></td></tr></tbody></table>

## Compute eddsa hash

```
const inputs = [
    new BN(ethUtil.toBuffer(request.exchange)).toString(),
    request.storageId,
    request.accountId,
    request.sellToken.tokenId,
    request.buyToken.tokenId,
    request.sellToken.volume,
    request.buyToken.volume,
    request.validUntil,
    request.maxFeeBips,
    request.fillAmountBOrS ? 1 : 0,
    new BN(ethUtil.toBuffer(request.taker)).toString(),
  ];
  const hasher = Poseidon.createHash(12, 6, 53);
  const hash = hasher(inputs).toString(10)
```
