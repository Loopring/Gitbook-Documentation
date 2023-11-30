---
description: Settle down an NFT trade which has two matched orders
---

# Trade NFT

## EndPoint

```
POST api/v3/nft/trade
```

## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr><tr><td>X-API-SIG</td><td><a href="../../../resources/signature/eddsa-signature/">EDDSA Signature</a>, <br><a href="../../../resources/request-signing/">sign the whole request</a></td><td>"0xccf0a141fce2dc5cbbd4f802c52220e9e2ce260e86704d6258603eb346eefe2d<br>4a450005c362b223b2842d087f7065ea5eee0314531adf6a580fce64c25dca81c"</td><td></td><td>Y</td></tr></tbody></table>

## Request

<table><thead><tr><th width="250.00000000000003">Query Param</th><th>Description</th><th>Example</th><th data-hidden></th><th data-hidden></th><th data-hidden></th></tr></thead><tbody><tr><td>maker</td><td><a href="../validate-nft-order/#request">NFTOrderRequest</a>, NFT maker order</td><td></td><td></td><td></td><td></td></tr><tr><td>makerFeeBips</td><td>maxFeeBips in maker object, should not smaller than royaltyPercentage of the <a href="../get-nft-info/#response-1">NFT info</a>, value range (in ten thousandths) 1 ~ 5000. the value = royaltyPercentage + extraFee. the extraFee is for nft submitter</td><td>100, means 1%</td><td></td><td></td><td></td></tr><tr><td>taker</td><td><a href="../validate-nft-order/#request">NFTOrderRequest</a>, NFT taker order</td><td></td><td></td><td></td><td></td></tr><tr><td>takerFeeBips</td><td>The taker feeBips, maxFeeBips in takers order. value range (in ten thousandths) 1 ~ 5000. taker fee need cover the trade fee and not smaller than 100.<br>You can get the tradeCost in <a href="../../../resources/fees/get-nft-order-fee/#response">get NFT order fee</a>, the value = ceiling(tradeCost/buyAmount)</td><td>100, means 1%</td><td></td><td></td><td></td></tr><tr><td>matchByTaker</td><td>use taker price to match the nft trade</td><td>true</td><td></td><td></td><td></td></tr></tbody></table>

## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>makerFills</td><td><a href="./#nfttradefill">NftTradeFil</a>, The fill status of the maker order</td><td>/</td><td><a href="https://docs.loopring.io/en/dex_apis/submitNftTrade.html#NftTradeFill">NftTrade<br>Fill</a></td><td>Y</td></tr><tr><td>takerFills</td><td><a href="./#nfttradefill">NftTradeFil</a>, The fill status of the taker order</td><td>/</td><td><a href="https://docs.loopring.io/en/dex_apis/submitNftTrade.html#NftTradeFill">NftTrade<br>Fill</a></td><td>Y</td></tr><tr><td>tradeHash</td><td>The trade hash which can be queried in loopring scan web.</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085"</td><td>string</td><td>Y</td></tr></tbody></table>

##

## Model

### **NftTokenAmountInfo**

Wrapper object used to describe a token associated with a certain quantity.

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>tokenId</td><td>The Loopring's NFT token identifier.</td><td>32769</td><td>integer</td><td>Y</td></tr><tr><td>amount</td><td><p>The amount of the NFT</p><p> token</p></td><td>"2"</td><td>string</td><td>Y</td></tr><tr><td>nftData</td><td>The Loopring's NFT token data identifier which is a hash string of NFT token address and NFT_ID</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa 8ca7100400f7c31085"</td><td></td><td></td></tr></tbody></table>

### **NftTradeFill**

Nft trade fill status

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>orderHash</td><td>The order hash</td><td></td><td>string</td><td>Y</td></tr><tr><td>sellFilled</td><td>The orders sell fill</td><td></td><td>string</td><td>Y</td></tr><tr><td>buyFilled</td><td>The orders buy fill</td><td></td><td>string</td><td>Y</td></tr><tr><td>fee</td><td>The orders fee</td><td></td><td>string</td><td>Y</td></tr></tbody></table>

## Compute EdDSA hash

```
const inputs = [
    request.taker.accountId,
    request.taker.sellToken.tokenId,
    request.taker.storageId,
    request.maker.accountId,
    request.maker.sellToken.tokenId,
    request.maker.storageId,
  ];
  
 const hasher = Poseidon.createHash(7, 6, 52);
 const hash = hasher(inputs).toString(10);
```
