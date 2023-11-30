# Get Assets

## EndPoint

```
GET /api/v3/user/balances
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey, can use a valid apiKey to get other address asset</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td>string</td><td>Y</td></tr></tbody></table>

\
Request
-------

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td><mark style="color:orange;">(Optional)</mark> AccountID, accountId or address is required</td><td>123456</td><td>integer</td><td>Y</td></tr><tr><td>address</td><td><mark style="color:orange;">(Optional)</mark> Address, accountId or address is required</td><td>"0x8656920c85342d646E5286Cb841F90209272ABeb"</td><td></td><td></td></tr><tr><td>tokens</td><td><mark style="color:orange;">(Optional)</mark> token ids in<br><a href="../../../resources/common-info/get-token-info/">exchange tokens</a></td><td>"0,1"</td><td>string</td><td>N</td></tr></tbody></table>



## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>Account ID</td><td>10110</td><td></td><td></td></tr><tr><td>tokenId</td><td>Token ID</td><td>10</td><td>integer</td><td>Y</td></tr><tr><td>total</td><td>Amount of the asset</td><td>"100"</td><td>string</td><td>Y</td></tr><tr><td>locked</td><td>The part of the total balance which is currently not liquid and not at the users disposal (because of pending withdrawals or orders for example)</td><td>"100"</td><td>string</td><td>Y</td></tr><tr><td>pending</td><td>Users <a href="./#pendingbalance">pending balances</a></td><td></td><td><a href="https://docs.loopring.io/en/dex_apis/getUserBalances.html#PendingBalance">Pending<br>Balance</a></td><td>Y</td></tr></tbody></table>



## Model

### **PendingBalance**

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>withdraw</td><td>Withdrawal pending balance which means the token is in withdrawal state but has not arrived at L1</td><td>"100000000000<br>00"</td><td>string</td><td>Y</td></tr><tr><td>deposit</td><td>Deposit pending balance which means the token is in deposit state but has not arrived at L2</td><td>"100000000000<br>00"</td><td>string</td><td>Y</td></tr></tbody></table>
