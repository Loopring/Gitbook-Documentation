---
description: Query NFT info by looprings nftData
---

# Get NFT Info

## EndPoint

```
GET /api/v3/nft/info/nfts
```

## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOayfPwnkQ6B6DQ6THZWbvrGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr></tbody></table>

## Request

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>nftDatas</td><td>users The Loopring's<a href="../../../glossary.md#eddsa-1"> NFT token data identifier</a>, separate by ",", max is 50</td><td>"0xf7c932351186c3a9053f31eefa16209c018f7f1dba8aa8ca7100400f7c31085,0xc3a9053f313eef7c932351ca7100400f7c186fa16209c018f7f1dba8aa831085"</td><td>integer</td><td>Y</td></tr></tbody></table>

## Response

List\[[NftInfo](./#nfttxdata)]



## Model

### NftInfo

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>nftData</td><td>NFT token <a href="../../../glossary.md#eddsa-1">nftData</a></td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085"</td><td>string</td><td>Y</td></tr><tr><td>minter</td><td>The minter of the NFT token. If withdraw and deposit, the minter would be the same as tokenAddress</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>nftType</td><td>NFT type</td><td>"ERC1155, ERC721"</td><td>string</td><td>Y</td></tr><tr><td>tokenAddress</td><td>NFT Token address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>nftId</td><td>NFT Id</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085"</td><td>string</td><td>Y</td></tr><tr><td>creatorFeeBips</td><td>(Deprecated)</td><td>10</td><td>integer</td><td>Y</td></tr><tr><td>royaltyPercentage</td><td>How much royalties to be paid to the creator. Ranging from 1-10</td><td>10</td><td></td><td></td></tr><tr><td>status</td><td>status</td><td>"true"</td><td>boolean</td><td>Y</td></tr><tr><td>nftFactory</td><td>counterFactual NFT factory</td><td>"0xbbbbca6a90<br>1c926f240b89<br>eacb641d8aec<br>7aeafd"</td><td>string</td><td>N</td></tr><tr><td>nftOwner</td><td>counterFactual NFT owner</td><td>"0xbbbbca6a90<br>1c926f240b89<br>eacb641d8aec<br>7aeafd"</td><td>string</td><td>N</td></tr><tr><td>nftBaseUri</td><td>counterFactual NFT base uri</td><td>""</td><td>string</td><td>N</td></tr><tr><td>royaltyAddress</td><td>Wallet address where the NFT royalties should be sent</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr><tr><td>originalMinter</td><td><mark style="color:orange;">(Optional)</mark> deprecated, will remove</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr><tr><td>originalRoyaltyPercentage</td><td><mark style="color:orange;">(Optional)</mark> deprecated, will remove</td><td></td><td></td><td></td></tr></tbody></table>

###
