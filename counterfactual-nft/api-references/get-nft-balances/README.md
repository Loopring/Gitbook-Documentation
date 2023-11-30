---
description: Query a wallet's NFT balance for token gating
---

# Get NFT Balances

## EndPoint

```
GET /api/v3/user/nft/base/balances
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey, can use a valid apiKey to get other address asset</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td>string</td><td>Y</td></tr></tbody></table>

\
Request
-------

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td><mark style="color:orange;">(Optional)</mark> AccountID, accountId or address is required</td><td>123456</td><td>integer</td><td>Y</td></tr><tr><td>address</td><td><mark style="color:orange;">(Optional)</mark> Address, accountId or address is required</td><td>"0x8656920c85342d646E5286Cb841F90209272ABeb"</td><td></td><td></td></tr><tr><td>offset</td><td><mark style="color:orange;">(Optional)</mark> Number of records to skip</td><td>10</td><td></td><td></td></tr><tr><td>limit</td><td><p><mark style="color:orange;">(Optional)</mark> Number of records to return.</p><p>Default is 20, max is 50</p></td><td>30</td><td></td><td></td></tr></tbody></table>

## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>totalNum</td><td>total amount of unique NFTs</td><td>100</td><td>integer</td><td>Y</td></tr><tr><td>data</td><td>list[<a href="./#balancedata">BalanceData</a>]</td><td></td><td></td><td></td></tr></tbody></table>

### **BalanceData**

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>total</td><td>total amount per NFT</td><td>4</td><td>string</td><td>Y</td></tr><tr><td>nftData</td><td>the nftData of the NFT token</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085"</td><td></td><td></td></tr></tbody></table>

