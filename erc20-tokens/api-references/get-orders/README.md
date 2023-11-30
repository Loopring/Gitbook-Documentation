# Get Orders

## EndPoint

```
GET /api/v3/orders
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOayfPwnkQ6B6DQ6THZWbvrGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr></tbody></table>



## Request

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>Account ID</td><td>10010</td><td>integer</td><td>N</td></tr><tr><td>market</td><td><mark style="color:orange;">(Optional)</mark> trading pair</td><td>"LRC-ETH"</td><td></td><td></td></tr><tr><td>start</td><td><mark style="color:orange;">(Optional)</mark> Start time in milliseconds<br>Default : 0L</td><td>1578558098000</td><td>integer</td><td>N</td></tr><tr><td>end</td><td><mark style="color:orange;">(Optional)</mark> End time in milliseconds<br>Default : 0L</td><td>1578558098000</td><td>integer</td><td>N</td></tr><tr><td>side</td><td><mark style="color:orange;">(Optional)</mark> "BUY" or "SELL"</td><td></td><td></td><td></td></tr><tr><td>status</td><td><mark style="color:orange;">(Optional)</mark> Order status. You can specify one of the following values: Allowable : ['processing', 'processed', 'failed', 'cancelled', 'cancelling', 'expired']</td><td></td><td></td><td></td></tr><tr><td>limit</td><td><mark style="color:orange;">(Optional)</mark> Number of records to return, max is 50 </td><td>20</td><td>integer</td><td>N</td></tr><tr><td>offset</td><td><mark style="color:orange;">(Optional)</mark> Number of records to skip<br>Default : 0L</td><td>1</td><td>integer</td><td>N</td></tr><tr><td>orderTypes</td><td>request.getOrders.orderTypes Allowable : ['LIMIT_ORDER', 'MAKER_ONLY', 'TAKER_ONLY', 'AMM']</td><td>"transfer,deposit"</td><td>string</td><td>N</td></tr><tr><td>extraOrderTypes</td><td><mark style="color:orange;">(Optional)</mark> can be "TRADITIONAL_ORDER", "STOP_LIMIT", default is "TRADITIONAL_ORDER"</td><td>"STOP_LIMIT"</td><td></td><td></td></tr></tbody></table>



## Response

| Field    | Description                    | Example |
| -------- | ------------------------------ | ------- |
| totalNum | total number                   |         |
| orders   | List\[[Order](./#transaction)] |         |



## Model

### Order

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>hash</td><td>Order hash</td><td>"0xfb5e711c2f<br>044e94322ed2<br>62229cd8f0d0<br>da00c22e1a00<br>a0f5d881e45a<br>38e1cf"</td><td>string</td><td>Y</td></tr><tr><td>clientOrderId</td><td>Order's client-side ID</td><td>"200310143135<br>081332"</td><td>string</td><td>Y</td></tr><tr><td>side</td><td>Order's side<br>Allowable : ['SELL', 'BUY']</td><td>"SELL"</td><td>string</td><td>Y</td></tr><tr><td>market</td><td>Trading pair</td><td>"LRC-ETH"</td><td>string</td><td>Y</td></tr><tr><td>price</td><td>Order price</td><td>"0.01987608"</td><td>string</td><td>Y</td></tr><tr><td>volumes</td><td><a href="./#ordervolumes">OrderVolume</a>, Wraps data regarding the orders volumes (base, quote, and filled.)</td><td>"0"</td><td><a href="https://docs.loopring.io/en/dex_apis/getOrders.html?h=api%2Fv3%2Forders#OrderVolumesV3">Order<br>Volumes<br>V3</a></td><td>Y</td></tr><tr><td>validity</td><td><a href="./#ordervalidity">OrderValidity</a>, Wraps data regarding time validity constraints (since and until)</td><td>"{start: 1234, end: 2345}"</td><td><a href="https://docs.loopring.io/en/dex_apis/getOrders.html?h=api%2Fv3%2Forders#OrderValidityV3">Order<br>Validity<br>V3</a></td><td>Y</td></tr><tr><td>orderType</td><td>Whether the order has to be treated as a limit, maker, or taker operation.<br>Allowable : ['LIMIT_ORDER', 'TAKER_ONLY', 'MAKER_ONLY']</td><td>"LIMIT_ORDER"</td><td>string</td><td>Y</td></tr><tr><td>tradeChannel</td><td>Order channel, can be ORDER_BOOK, AMM_POOL, MIXED<br>Allowable : ['ORDER_BOOK', 'AMM_POOL', 'MIXED']</td><td>"ORDER_BOOK"</td><td>string</td><td>Y</td></tr><tr><td>status</td><td>Order status<br>Allowable : ['processing', 'processed', 'cancelling', 'cancelled', 'expired', 'waiting']</td><td>"processing"</td><td>string</td><td>Y</td></tr><tr><td>storageInfo</td><td><mark style="color:orange;">(Optional)</mark> <a href="./#storageinfo">storage info</a></td><td></td><td><a href="https://docs.loopring.io/en/dex_apis/getOrders.html?h=api%2Fv3%2Forders#StorageInfo">Storage<br>Info</a></td><td>N</td></tr><tr><td>extraOrderInfo</td><td><mark style="color:orange;">(Optional)</mark>  <a href="./#extraorderinfo">extra order info</a></td><td></td><td></td><td></td></tr></tbody></table>



### **OrderVolumes**

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>baseAmount</td><td>The amount of base tokens involved in the order.</td><td>"0"</td><td>string</td><td>Y</td></tr><tr><td>quoteAmount</td><td>The amount of quote tokens involved in the order.</td><td>"0"</td><td>string</td><td>Y</td></tr><tr><td>baseFilled</td><td>The amount of requested base tokens filled in the order.</td><td>"0"</td><td>string</td><td>Y</td></tr><tr><td>quoteFilled</td><td>The amount of requested quote tokens filled in the order.</td><td>"0"</td><td>string</td><td>Y</td></tr><tr><td>fee</td><td>The amount of quote or base token amount used to pay for the orders fee. Whether this data refers to the base or quote token, one can find out by looking at the orders side</td><td>"0"</td><td>string</td><td>Y</td></tr></tbody></table>



## **OrderValidity**

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>start</td><td>Timestamp from when the order officially becomes valid and fillable</td><td>0</td><td>integer</td><td>Y</td></tr><tr><td>end</td><td>Timestamp from when the order ceases to be valid and fillable</td><td>0</td><td>integer</td><td>Y</td></tr></tbody></table>



## storageInfo

| Field     | Description | Example |
| --------- | ----------- | ------- |
| accountId | account ID  | 10110   |
| tokenId   | token ID    | 0       |
| storageId | storageId   | 1       |



### extraOrderInfo

| Field       | Description                                                       | Example                   |
| ----------- | ----------------------------------------------------------------- | ------------------------- |
| isTriggered | triggerd or not                                                   | false                     |
| stopPrice   | stop price                                                        | "0.36"                    |
| stopSide    | stop side, "GREAT\_THAN\_AND\_EQUAL" or  "LESS\_THAN\_AND\_EQUAL" | "GREAT\_THAN\_AND\_EQUAL" |

