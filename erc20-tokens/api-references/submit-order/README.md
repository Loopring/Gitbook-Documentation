---
description: Place an order
---

# Submit Order

## EndPoint

```
POST api/v3/order
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr></tbody></table>



## Request

<table><thead><tr><th width="150">Query Param</th><th>Description</th><th>Example</th><th data-hidden></th><th data-hidden></th><th data-hidden></th></tr></thead><tbody><tr><td>exchange</td><td>exchangeAddress in <a href="../../../resources/common-info/get-exchange-info/">exchange info</a></td><td></td><td></td><td></td><td></td></tr><tr><td>accountId</td><td>account ID</td><td></td><td></td><td></td><td></td></tr><tr><td>sellToken</td><td><a href="./#tokenvolume">tokenVolume</a>，sell tokenId and volume</td><td></td><td></td><td></td><td></td></tr><tr><td>buyToken</td><td><a href="./#tokenvolume">tokenVolume</a>，buy tokenId and volume</td><td></td><td></td><td></td><td></td></tr><tr><td>storageId</td><td>order of <a href="../../../resources/storage-id/">storage Id</a>, sellTokenId is the tokenId in sellToken</td><td>2</td><td></td><td></td><td></td></tr><tr><td>validUntil</td><td>Timestamp for order to become invalid, seconds</td><td><p></p><p>normally current time + 2 months</p></td><td></td><td></td><td></td></tr><tr><td>maxFeeBips</td><td>Maximum order fee that the user can accept, value range (in ten thousandths) 1 ~ 5000</td><td>10(means 0.1%)</td><td></td><td></td><td></td></tr><tr><td>eddsaSignature</td><td><a href="../../../resources/signature/eddsa-signature/">eddsa signature</a><br>of the <a href="./#compute-eddsa-hash">eddsa hash</a></td><td></td><td></td><td></td><td></td></tr><tr><td>fillAmountBOrS</td><td><mark style="color:orange;">(Optional)</mark> Fill size by buy token or by sell token</td><td>false</td><td></td><td></td><td></td></tr><tr><td>clientOrderId</td><td><mark style="color:orange;">(Optional)</mark> An arbitrary, client-set unique order identifier, max length is 120 bytes</td><td></td><td></td><td></td><td></td></tr><tr><td>orderType</td><td><mark style="color:orange;">(Optional)</mark> Order types, can be AMM, LIMIT_ORDER, MAKER_ONLY or TAKER_ONLY  default is LIMIT_ORDER. If it's AMM, orderType will set to TAKER_ONLY and tradeChannel will set to MIXED</td><td>"LIMIT_ORDER"</td><td></td><td></td><td></td></tr><tr><td>tradeChannel</td><td><mark style="color:orange;">(Optional)</mark> Order channel, can be ORDER_BOOK, AMM_POOL or MIXED, default is MIXED. If it's AMM_POOL, orderType will set to TAKER_ONLY and tradeChannel will set to MIXED</td><td>"MIXED"</td><td></td><td></td><td></td></tr><tr><td>poolAddress</td><td><mark style="color:orange;">(Optional)</mark> The AMM pool address if order type is AMM</td><td></td><td></td><td></td><td></td></tr><tr><td>affiliate</td><td><mark style="color:orange;">(Optional)</mark> An accountID who will receive a share of the fee of this order at the end of monthly distribution.<br>Need contact us to add the accountId in whitelist.</td><td>10110</td><td></td><td></td><td></td></tr><tr><td>extraOrderType</td><td><mark style="color:orange;">(Optional)</mark> extra type, default is "TRADITIONAL_ORDER", can be "STOP_LIMIT"</td><td>STOP_LIMIT</td><td></td><td></td><td></td></tr><tr><td>stopPrice</td><td><mark style="color:orange;">(Optional)</mark> stop price</td><td>"0.36"</td><td></td><td></td><td></td></tr><tr><td>stopSide</td><td><mark style="color:orange;">(Optional)</mark> can be "GREAT_THAN_AND_EQUAL", "LESS_THAN_AND_EQUAL"</td><td>"GREAT_THAN_AND_EQUAL"</td><td></td><td></td><td></td></tr></tbody></table>



## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>hash</td><td>The hash identifier set by the user at the time of submission, can use this hash to get the order info</td><td>"0x1d923ca7834dc90484fa2eb611f0f0bc7e741bb107007ebea19ba8caeab4f9d3"</td><td>string</td><td>Y</td></tr><tr><td>clientOrderId</td><td>The clientOrderId of the submitted order</td><td></td><td></td><td></td></tr><tr><td>status</td><td>Order status of submit order response Allowable : ['processing', 'processed', 'cancelling', 'cancelled', 'expired', 'failed']</td><td>"processing"</td><td>string</td><td>Y</td></tr><tr><td>isIdempotent</td><td>Idempotent of submit transfer response, submit same transfer again idempotent will be true</td><td>"false"</td><td>boolean</td><td>Y</td></tr></tbody></table>



## Model

### TokenVolume

Wrapper object used to describe a token associated with a certain quantity.

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>tokenId</td><td>The Loopring's token identifier.</td><td>0</td><td>integer</td><td>Y</td></tr><tr><td>volume</td><td>The volume of the token</td><td>"100000000000<br>0"</td><td>string</td><td>Y</td></tr></tbody></table>



## Compute EdDSA hash

```
const inputs = [
      orderRequest.exchange,
      orderRequest.storageId,
      orderRequest.accountId,
      orderRequest.sellToken.tokenId,
      orderRequest.buyToken.tokenId,
      orderRequest.sellToken.volume,
      orderRequest.buyToken.volume,
      orderRequest.validUntil,
      orderRequest.maxFeeBips,
      orderRequest.fillAmountBOrS ? 1 : 0,
      orderRequest.taker,
    ];
const hasher = Poseidon.createHash(inputs.length + 1, 6, 53);
const hash = hasher(inputs).toString(10);
```
