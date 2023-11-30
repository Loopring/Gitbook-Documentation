---
description: Get NFT Trade History
---

# Get NFT Trade History

## EndPoint

```
GET /api/v3/user/nft/trades
```

## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOayfPwnkQ6B6DQ6THZWbvrGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr></tbody></table>

## Request

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>users accountId.</td><td>10001</td><td>integer</td><td>Y</td></tr><tr><td>nftData</td><td><mark style="color:orange;">(Optional)</mark> the nftData of the NFT token</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085"</td><td>string</td><td>N</td></tr><tr><td>orderHash</td><td><mark style="color:orange;">(Optional)</mark> NFT order hash</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085"</td><td>string</td><td>N</td></tr><tr><td>tradeHash</td><td><mark style="color:orange;">(Optional)</mark> NFT trade hash</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085"</td><td></td><td></td></tr><tr><td>start</td><td><mark style="color:orange;">(Optional)</mark> Start time in milliseconds</td><td>1567053142000</td><td>integer</td><td>N</td></tr><tr><td>end</td><td><mark style="color:orange;">(Optional)</mark> End time in milliseconds</td><td>1567053142000</td><td>integer</td><td>N</td></tr><tr><td>startId</td><td><mark style="color:orange;">(Optional)</mark> The begin id of the query.</td><td>12</td><td>integer</td><td>N</td></tr><tr><td>limit</td><td><mark style="color:orange;">(Optional)</mark> Number of records to return, max is 50</td><td>20</td><td>integer</td><td>N</td></tr><tr><td>offset</td><td><mark style="color:orange;">(Optional)</mark> Number of records to skip</td><td>1</td><td></td><td></td></tr><tr><td>isASC</td><td><mark style="color:orange;">(Optional)</mark> Sort records in ascending order</td><td>true</td><td></td><td></td></tr></tbody></table>

## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>totalNum</td><td>total number</td><td>100</td><td>integer</td><td>Y</td></tr><tr><td>trades</td><td>List[<a href="./#response">TradeInfo</a>], Trade info</td><td></td><td>List[List[string]]</td><td>Y</td></tr></tbody></table>



## Model

### TradeInfo

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>id</td><td>the index</td><td>"1"</td><td>integer</td><td>Y</td></tr><tr><td>hash</td><td>nft trade hash</td><td>"0x2d4dcc071cb511cca912574aecb0076ba57e057b0716efb849b62da50926aa57"</td><td>List[List[string]]</td><td>Y</td></tr><tr><td>sellOrderHash</td><td>sell order hash</td><td>"0x199af4d4dcfbb7acae35d3b55a0ad99a0759f37dcef3388497e07008ec91a7d1"</td><td></td><td></td></tr><tr><td>buyOrderHash</td><td>buy order hash</td><td>"0x28b8415bd05dd7c68385e37870b6d9177cf7f8c2ba2e8ab151661114d546e799"</td><td></td><td></td></tr><tr><td>price</td><td>the price</td><td>"1.00000000"</td><td></td><td></td></tr><tr><td>nftData</td><td></td><td>"0x1a2001aac7a1fd00cef07889cdb67b1355f86e5bc9df71cfa44fa1c7b49f598f"</td><td></td><td></td></tr><tr><td>nftAmount</td><td>nft amount</td><td>"1"</td><td></td><td></td></tr><tr><td>nftTokenId</td><td>nft tokenId</td><td>"32768"</td><td></td><td></td></tr><tr><td>erc20TokenId</td><td>erc20 tokenId</td><td>"0"</td><td></td><td></td></tr><tr><td>sellFeeAmount</td><td>sell order fee amount</td><td>"10000000000000000"</td><td></td><td></td></tr><tr><td>buyFeeAmount</td><td>buy order fee amount</td><td>"1000000000000000"</td><td></td><td></td></tr><tr><td>blockId</td><td>the trade in layer2 block, useless now</td><td>"0"</td><td></td><td></td></tr><tr><td>indexInBlock</td><td>the index in block, useless now</td><td>"0"</td><td></td><td></td></tr><tr><td>sellAccountId</td><td>seller accountId</td><td>"12454"</td><td></td><td></td></tr><tr><td>buyAccountId</td><td>buyer accountId</td><td>"10488"</td><td></td><td></td></tr><tr><td>sellStorageId</td><td>seller storageId</td><td>"54"</td><td></td><td></td></tr><tr><td>buyStorageId</td><td>buyer storageId</td><td>"64"</td><td></td><td></td></tr><tr><td>createdAt</td><td>timestamp</td><td>"1653635906103"</td><td></td><td></td></tr><tr><td>submitter_accountId</td><td>the accountId submitted the nft trade</td><td>"10011"</td><td></td><td></td></tr><tr><td>sellAddress</td><td>seller address</td><td>"0x8656920c85342d646E5286Cb841F90209272ABeb"</td><td></td><td></td></tr><tr><td>buyAddress</td><td>buyer address</td><td>"0x5666920c85342d646E4392Lv457G79032322Z7dk"</td><td></td><td></td></tr></tbody></table>

###

