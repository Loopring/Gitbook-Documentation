---
description: get fee of updateAccount, transfer, withdraw. etc
---

# GET ERC20 Offchain Fee

## EndPoint

```
GET api/v3/user/offchainFee
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td>string</td><td>Y</td></tr></tbody></table>



## Request

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>Account ID</td><td>10110</td><td>integer</td><td>Y</td></tr><tr><td>requestType</td><td>Off-chain request type<br>Allowable : ['0:ORDER', '1:OFFCHAIN_WITHDRAWAL', '2:UPDATE_ACCOUNT', '3:TRANSFER', '4:FAST_OFFCHAIN_WITHDRAWAL', '5:OPEN_ACCOUNT', '6:AMM_EXIT', '7:DEPOSIT', '8:AMM_JOIN', '15:TRANSFER_AND_UPDATE_ACCOUNT']</td><td>1</td><td>integer</td><td>Y</td></tr><tr><td>tokenSymbol</td><td>(Optional)The token symbol, needed when requestType is 1 or 4 </td><td>"LRC"</td><td>string</td><td>N</td></tr><tr><td>amount</td><td>(Optional) The amount to withdraw</td><td>"10000000000000"</td><td>string</td><td>N</td></tr></tbody></table>



## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>gasPrice</td><td>gasPrice when calculate the fee</td><td>2194508101</td><td>string</td><td>Y</td></tr><tr><td>fees</td><td>List[<a href="./#tokenfee">TokenFee</a>]</td><td></td><td>string</td><td>Y</td></tr></tbody></table>



## Model

### TokenFee

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>token</td><td>fee token</td><td>"ETH"</td><td>string</td><td>Y</td></tr><tr><td>fee</td><td>fee amount</td><td>"200000000000<br>0000"</td><td>string</td><td>Y</td></tr><tr><td>discount</td><td>token discount. 0.8 means 80% of original fee</td><td>1.0</td><td>number</td><td>Y</td></tr></tbody></table>
