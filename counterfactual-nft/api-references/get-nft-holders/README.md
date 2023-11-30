---
description: Query NFT holders by Looprings nftData
---

# Get NFT Holders

## EndPoint

```
GET /api/v3/nft/info/nftHolders
```

## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOayfPwnkQ6B6DQ6THZWbvrGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr></tbody></table>

## Request

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>nftData</td><td>The Loopring's NFT token data identifier which is a hash string of the NFT token address and NFT_ID</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085"</td><td>string</td><td>Y</td></tr><tr><td>offset</td><td><mark style="color:orange;">(Optional)</mark> Number of records to skip</td><td>0</td><td>integer</td><td>N</td></tr><tr><td>limit</td><td><mark style="color:orange;">(Optional)</mark> Number of records to return, default is 20, max is 50</td><td>10</td><td>integer</td><td>N</td></tr></tbody></table>

\


## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>totalNum</td><td>total number</td><td> 20</td><td>integer</td><td>Y</td></tr><tr><td>nftHolders</td><td>List[<a href="./#nftholder">NftHolder</a>], NFT holders info</td><td>/</td><td>List[<a href="https://docs.loopring.io/en/dex_apis/getNftHolders.html#NftHolder">Nft<br>Holder</a>]</td><td>Y</td></tr></tbody></table>

##

## Model

### NftHolder

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>account Id</td><td>10010</td><td>integer</td><td>Y</td></tr><tr><td>address</td><td>account address</td><td>0x72aa8A62087348c4a67EcaE15370f34586a7553E</td><td></td><td></td></tr><tr><td>tokenId</td><td>The Loopring's NFT token identifier.</td><td>32768</td><td>integer</td><td>Y</td></tr><tr><td>amount</td><td>The amount of the NFT token</td><td>"1"</td><td>string</td><td>Y</td></tr></tbody></table>
