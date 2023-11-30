# Get token info

## EndPoint

```
GET /api/v3/exchange/tokens
```



## **Response**

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>type</td><td>Token Type<br>Allowable : ['ERC20', 'ETH']</td><td>"ERC20"</td><td>string</td><td>Y</td></tr><tr><td>tokenId</td><td>Token's numeric ID</td><td>2</td><td>integer</td><td>Y</td></tr><tr><td>symbol</td><td>Token symbol</td><td>"LRC"</td><td>string</td><td>Y</td></tr><tr><td>name</td><td>Token name</td><td>"Loopring"</td><td>string</td><td>Y</td></tr><tr><td>address</td><td>Token ERC20 contract address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>decimals</td><td>Token decimals</td><td>18</td><td>integer</td><td>Y</td></tr><tr><td>precision</td><td>Max decimals that relayer uses for the token, smaller amount will be treated as zero.</td><td>6</td><td>integer</td><td>Y</td></tr><tr><td>precisionForOrder</td><td>Max decimals that relayer uses for the token, smaller amount will be treated as zero.</td><td>6</td><td>integer</td><td>Y</td></tr><tr><td><a href="./#orderamount">orderAmounts</a></td><td>The amount requirements for submitting orders.</td><td>"{min:100000, max:900000, dust:10}"</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getTokens.html#OrderAmountsV3">Order<br>Amounts<br>V3</a></td><td>Y</td></tr><tr><td><a href="./#orderamount">luckyTokenAmounts</a></td><td>field.TokenInfoV3.luckyTokenAmounts</td><td>"{min:100000, max:900000, dust:10}"</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getTokens.html#OrderAmountsV3">Order<br>Amounts<br>V3</a></td><td>Y</td></tr><tr><td>fastWithdrawLimit</td><td>The maximum amount for single fast withdrawal</td><td>"100000000000<br>0000"</td><td>string</td><td>Y</td></tr><tr><td><a href="./#gasamountlimit">gasAmounts</a></td><td>The gas amount requirements for user requests</td><td>"{distributio<br>nGas:100000, depositGas:1<br>50000}"</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getTokens.html#GasAmountLimitV3">Gas<br>Amount<br>LimitV3</a></td><td>Y</td></tr><tr><td>enabled</td><td>Whether the token is currently enabled for deposits and withdrawals.</td><td>"true"</td><td>boolean</td><td>Y</td></tr></tbody></table>



## Model

### **OrderAmount**

Contains information about the order amounts that are valid for usage with the token in order-related APIs.



<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>minimum</td><td>The minimum amount enforced when submitting orders for the token.</td><td>"100000000000<br>00000"</td><td>string</td><td>Y</td></tr><tr><td>maximum</td><td>The maximum amount enforced when submitting orders for the token.</td><td>"100000000000<br>0000000"</td><td>string</td><td>Y</td></tr><tr><td>dust</td><td>The dust amount enforced when submitting orders for the token.</td><td>"100000000000<br>0000"</td><td>string</td><td>Y</td></tr></tbody></table>

### **GasAmountLimit**

Contains information about the gas amounts required by ETH L1 requests.

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>distribution</td><td>The gas amount for withdrawal</td><td>"100000000000<br>0000"</td><td>string</td><td>Y</td></tr><tr><td>deposit</td><td>The gas amount for deposit</td><td>"100000000000<br>0000"</td><td>string</td><td>Y</td></tr></tbody></table>
