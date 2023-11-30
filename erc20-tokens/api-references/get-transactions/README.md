---
description: Get history for deposit, transfer and/or withdraw
---

# Get Transactions

## EndPoint

```
GET /api/v3/user/transactions
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOayfPwnkQ6B6DQ6THZWbvrGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr></tbody></table>



## Request

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>Account ID</td><td>10010</td><td>integer</td><td>N</td></tr><tr><td>start</td><td><mark style="color:orange;">(Optional)</mark> Start time in milliseconds<br>Default : 0L</td><td>1578558098000</td><td>integer</td><td>N</td></tr><tr><td>end</td><td><mark style="color:orange;">(Optional)</mark> End time in milliseconds<br>Default : 0L</td><td>1578558098000</td><td>integer</td><td>N</td></tr><tr><td>limit</td><td><mark style="color:orange;">(Optional)</mark> Number of records to return, max is 50 </td><td>20</td><td>integer</td><td>N</td></tr><tr><td>tokenSymbol</td><td><mark style="color:orange;">(Optional)</mark> Token to filter. If you want to return deposit records for all tokens, omit this parameter</td><td>"LRC"</td><td>string</td><td>N</td></tr><tr><td>offset</td><td><mark style="color:orange;">(Optional)</mark> Number of records to skip<br>Default : 0L</td><td>1</td><td>integer</td><td>N</td></tr><tr><td>types</td><td>types, in "transfer,deposit,offchain_withdrawal,change_password", (split by ,)</td><td>"transfer,deposit"</td><td>string</td><td>N</td></tr><tr><td>hashes</td><td>The hashes (split by ,) of the transactions, normally its L2 tx hash, except the deposit which uses L1 tx hash.</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085"</td><td>string</td><td>N</td></tr></tbody></table>



## Response

List\[[Transaction](./#nftinfo)]



## Model

### Transaction

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>id</td><td>Unique id</td><td>1</td><td>integer</td><td>Y</td></tr><tr><td>hash</td><td>L2 hash</td><td>"0x9d114267e8b261457d567093c13cf3deea5f14c9235be26c6fa833dba12a9632"</td><td>string</td><td>Y</td></tr><tr><td>txType</td><td>User transaction type</td><td><p>"DEPOSIT"</p><p>"ONCHAIN_WITHDRAWAL"</p><p>"TRANSFER"</p><p>"CHANGE_PWD"</p><p>"CREATE_ACCOUNT"</p><p>"OFFCHAIN_WITHDRAWAL"</p><p>"AMM_JOIN"</p><p>"AMM_EXIT"</p></td><td>string</td><td>Y</td></tr><tr><td>symbol</td><td>Token symbol</td><td>"LRC"</td><td>string</td><td>Y</td></tr><tr><td>amount</td><td>Amount requested by the user</td><td>"100000000000<br>0000000"</td><td>string</td><td>Y</td></tr><tr><td>txHsh</td><td>Layer 1 hash</td><td>"0x9d114267e8b261457d567093c13cf3deea5f14c9235be26c6fa833dba12a9632"</td><td>string</td><td>N</td></tr><tr><td>senderAddress</td><td>sender address</td><td>"0x0306b9d5c9Ed358FC7b77780bACD15398D242f26"</td><td></td><td></td></tr><tr><td>receiver</td><td>Receiver account id</td><td>10110</td><td>integer</td><td>N</td></tr><tr><td>receiverAddress</td><td>The transfer receiver's address</td><td>"0x0306b9d5c9Ed358FC7b77780bACD15398D242f26"</td><td>string</td><td>N</td></tr><tr><td>feeTokenSymbol</td><td>Fee token symbol</td><td>"ETH"</td><td>string</td><td>Y</td></tr><tr><td>feeAmount</td><td>Fee amount in wei</td><td>"100000000000<br>0000"</td><td>string</td><td>Y</td></tr><tr><td>status</td><td>Current status<br>Allowable : ['processing', 'processed', 'received', 'failed']</td><td>"processing"</td><td>string</td><td>Y</td></tr><tr><td>progress</td><td>Progress</td><td>"100%"</td><td>string</td><td>Y</td></tr><tr><td>timestamp</td><td>Create time</td><td>1578572292000</td><td>integer</td><td>Y</td></tr><tr><td>updatedAt</td><td>Update time</td><td>1578572292000</td><td>integer</td><td>Y</td></tr><tr><td>memo</td><td>memo</td><td>"Air Drop"</td><td>string</td><td>N</td></tr><tr><td>withdrawalInfo</td><td><a href="./#undefined">withdraw info</a></td><td>/</td><td>integer</td><td>Y</td></tr><tr><td>storageInfo</td><td><a href="./#storageinfo">storage info</a><br>can link to explorer.loopring.io</td><td></td><td></td><td></td></tr></tbody></table>



## withdrawInfo

| Field          | Description      | Example |
| -------------- | ---------------- | ------- |
| recipient      | receiver address |         |
| fastStatus     |                  |         |
| distributeHash | Layer 1 tx hash  |         |



## storageInfo

| Field     | Description | Example |
| --------- | ----------- | ------- |
| accountId | account ID  | 10110   |
| tokenId   | token ID    | 0       |
| storageId | storageId   | 1       |
