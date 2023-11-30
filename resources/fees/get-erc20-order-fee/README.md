---
description: ERC20 get fee of order
---

# GET ERC20 Order Fee

This API returns 2 minimum amounts, one is based on users fee rate, the other is based on the maximum fee bips which is 0.6%. In other words, if a user wants to keep the fee rate, the minimum order is higher, otherwise, the user needs to pay more but can place lower order amounts.

## EndPoint

```
GET api/v3/user/orderUserRateAmount
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td>string</td><td>Y</td></tr></tbody></table>



## Request

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>Account ID</td><td>10010</td><td>integer</td><td>Y</td></tr><tr><td>market</td><td>List of markets to be queried separated by ","</td><td>"LRC-ETH"</td><td>string</td><td>Y</td></tr></tbody></table>



## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>gasPrice</td><td>The gas price use to calculate amount</td><td>"10000000000"</td><td>string</td><td>N</td></tr><tr><td>amounts</td><td>List[<a href="./#tokenamount">Token<br>Amount]</a>, Amounts</td><td>/</td><td>List[<a href="https://docs-uat.loopring.io/en/dex_apis/getOrderUserRateAmount.html#TokenAmount">Token<br>Amount</a>]</td><td>N</td></tr><tr><td>cacheOverdueAt</td><td>Cached price data overdue time</td><td>1614683483382</td><td>integer</td><td>N</td></tr></tbody></table>



## Model

### TokenAmount

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>tokenSymbol</td><td>Token</td><td>"LRC"</td><td>string</td><td>N</td></tr><tr><td>discount</td><td>Fee rate discount</td><td>1.0</td><td>number</td><td>N</td></tr><tr><td>baseOrderInfo</td><td><a href="./#orderinfo">OrderInfo</a>, The minimum amount accord with minimum fee rate</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getOrderUserRateAmount.html#OrderInfo">Order<br>Info</a></td><td>N</td></tr><tr><td>userOrderInfo</td><td><a href="./#orderinfo">OrderInfo</a>, The minimum amount accord with user fee rate</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getOrderUserRateAmount.html#OrderInfo">Order<br>Info</a></td><td>N</td></tr><tr><td>tradeCost</td><td><a href="../../advanced/submit-erc20-order.md#how-to-use-tradecost">trade cost</a></td><td>"12474000057750"</td><td></td><td></td></tr></tbody></table>



### OrderInfo

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>minAmount</td><td>The minimum amount of buy</td><td>"10000000000"</td><td>string</td><td>N</td></tr><tr><td>makerRate</td><td>Maker rate</td><td>0</td><td>integer</td><td>N</td></tr><tr><td>takerRate</td><td>Taker rate</td><td>30, means 0.3%</td><td>integer</td><td>N</td></tr></tbody></table>



### OrderAmount

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>minimum</td><td>The minimum amount enforced when submitting orders for the token.</td><td>"100000000000<br>00000"</td><td>string</td><td>Y</td></tr><tr><td>maximum</td><td>The maximum amount enforced when submitting orders for the token.</td><td>"100000000000<br>0000000"</td><td>string</td><td>Y</td></tr><tr><td>dust</td><td>The dust amount enforced when submitting orders for the token.</td><td>"100000000000<br>0000"</td><td>string</td><td>Y</td></tr></tbody></table>
