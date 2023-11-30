---
description: get NFT order fee
---

# GET NFT Order Fee

## EndPoint

```
GET api/v3/nft/info/orderUserRateAmount
```



`minAmount` is the `minFee` under the basic `feeRate` of the user, `tradeCosts` is the cost of L2 trade settlement, also it returns the market order requirements: the min/max order amount. So a valid order should meet these 3 requirements:.

1. order.maxFeeBips >= feeRate.rate and order.amount >= minAmounts.
2. order.amount \* order.maxFeeBips > tradeCosts if order.amount < minAmounts.
3. marketOrderInfo.min <= order.amount <= marketOrderInfo.max.

These amounts change according to ETH gas price and are refreshed every 15 mins.



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td>string</td><td>Y</td></tr></tbody></table>



## Request

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>Account ID</td><td>10010</td><td>integer</td><td>Y</td></tr><tr><td>nftTokenAddress</td><td>NFT token address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec 7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>feeTokenSymbol</td><td>Fee token symbol</td><td>"ETH"</td><td>integer</td><td>Y</td></tr></tbody></table>



## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>nftTokenAddress</td><td>NFT token address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>feeRate</td><td>fee rate</td><td>20</td><td>integer</td><td>Y</td></tr><tr><td>amounts</td><td><a href="./#feetokenamount">FeeTokenAmount</a></td><td>/</td><td>List[<a href="https://docs-uat.loopring.io/en/dex_apis/getNftOrderUserRateAmount.html#FeeTokenAmount">FeeToken<br>Amount</a>]</td><td>Y</td></tr><tr><td>gasPrice</td><td>gas price</td><td>"10000000000"</td><td>string</td><td>Y</td></tr><tr><td>cacheOverdueAt</td><td>Cached price data overdue time</td><td>1632365568</td><td>integer</td><td>Y</td></tr></tbody></table>



## Model

### **FeeTokenAmount**

The result of query NFT market minimum fee tokens amount

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>feeTokenSymbol</td><td>Fee token symbol</td><td>"ETH"</td><td>string</td><td>Y</td></tr><tr><td>minAmount</td><td>The minimum quote token amount to place an NFT order</td><td>/</td><td>string</td><td>Y</td></tr><tr><td>tradeCost</td><td>The base cost of trade settlement. Can use this tradeCost/buyAmount to calculate taker maxFeeBips</td><td>/</td><td>string</td><td>Y</td></tr><tr><td>marketOrderInfo</td><td><a href="./#orderamountsv3">OrderAmount</a>, the market info of the NFT market include min/max/dust order amount limitations.</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getNftOrderUserRateAmount.html#OrderAmountsV3">Order<br>Amounts<br>V3</a></td><td>Y</td></tr></tbody></table>



### **OrderAmounts**

Contains information about the order amounts that are valid for usage with the token in order-related APIs.

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>minimum</td><td>The minimum amount enforced when submitting orders for the token.</td><td>"100000000000<br>00000"</td><td>string</td><td>Y</td></tr><tr><td>maximum</td><td>The maximum amount enforced when submitting orders for the token.</td><td>"100000000000<br>0000000"</td><td>string</td><td>Y</td></tr><tr><td>dust</td><td>The dust amount enforced when submitting orders for the token.</td><td>"100000000000<br>0000"</td><td>string</td><td>Y</td></tr></tbody></table>
