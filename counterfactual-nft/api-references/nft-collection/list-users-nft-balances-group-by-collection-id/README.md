---
description: View user's NFT balance group by collection
---

# List user's NFT balances group by Collection ID



## Endpoint

```
GET /api/v3/user/collection/details
```



## Header

|   Field   | Description | Example                                                            |
| :-------: | ----------- | ------------------------------------------------------------------ |
| X-API-KEY | ApiKey      | "HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN" |

##

## **Request**

|       Query Param       | Description                                   | Example                                      |
| :---------------------: | --------------------------------------------- | -------------------------------------------- |
|        accountId        | User account Id                               | 10001                                        |
|          offset         | (Optional)                                    | 0                                            |
|          limit          | (Optional)                                    | 10                                           |
|    nonZero (Optional)   | Only return non-zero nfts                     | true                                         |
| tokenAddress (Optional) | Only return collections of this token address | fe0x1abe8e24312e9fe614b5c9c67b472b3ecb3b8788 |

##

## **Response**

|    Field    | Description                        | Example |
| :---------: | ---------------------------------- | ------- |
| collections | See [Collection](broken-reference) |         |

### **Collection**

|       Field       | Description                                                                                                                                                                                                                                                                                                                                                                                                               | Example                                                                                                                                                |
| :---------------: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
|         id        | Unique collection Id                                                                                                                                                                                                                                                                                                                                                                                                      | 256                                                                                                                                                    |
|       owner       | Owner address                                                                                                                                                                                                                                                                                                                                                                                                             | "0x3be20a5500a331ef148f1aca64e326cd0b605a4b"                                                                                                           |
|        name       | Collection name                                                                                                                                                                                                                                                                                                                                                                                                           | "test1127"                                                                                                                                             |
|  contractAddress  | ERC1155 nft token address to be deployed on L1                                                                                                                                                                                                                                                                                                                                                                            | "0x4a71d8b79ab6d9ae89e6709a54e53db9c9e27e49"                                                                                                           |
| collectionAddress | URL of collection metadata, if this collection is created via loopring.io web app, `collectionAddress` will start with `0x`, and it can be visited on the browser via appending prefix `https://nftinfos.loopring.io/` to the `collectionAddress`, for example, `https://nftinfos.loopring.io/0x9717fa2a7d827b3db111be23938c95d14b875863`. Otherwise, it may be in the format of ipfs `ipfs://...` or https `https://...` | "0x9717fa2a7d827b3db111be23938c95d14b875863" or "https://api.nft.gamestop.com/getCollectionMetadata?collectionId=a07373e5-989d-4746-909b-e87430b5947c" |
|      baseUri      | Generated by Loopring                                                                                                                                                                                                                                                                                                                                                                                                     | "ipfs://0x26ae6d3096348959d033b32ef635b58c0b50d5cb2165debafbb7e6eef783fd9e"                                                                            |
|     nftFactory    | NFT factory contract address of this colleciton                                                                                                                                                                                                                                                                                                                                                                           | "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281"                                                                                                           |
|    description    | Text                                                                                                                                                                                                                                                                                                                                                                                                                      | ""                                                                                                                                                     |
|       avatar      | Ipfs URI or URL of collection image                                                                                                                                                                                                                                                                                                                                                                                       | "ipfs://QmZop7r8RQkB3L9BNfkKsZfY82kTVoPQyaSiZsTeKgTDij"                                                                                                |
|       banner      | Ipfs URI or URL of collection image                                                                                                                                                                                                                                                                                                                                                                                       | "ipfs://QmZop7r8RQkB3L9BNfkKsZfY82kTVoPQyaSiZsTeKgTDij"                                                                                                |
|     thumbnail     | Ipfs URI or URL of collection image                                                                                                                                                                                                                                                                                                                                                                                       | "ipfs://QmZop7r8RQkB3L9BNfkKsZfY82kTVoPQyaSiZsTeKgTDij"                                                                                                |
|      tileUri      | Ipfs URI or URL of collection image                                                                                                                                                                                                                                                                                                                                                                                       | "ipfs://QmZop7r8RQkB3L9BNfkKsZfY82kTVoPQyaSiZsTeKgTDij",                                                                                               |
|       cached      | Cached collection image URL read and stored by loopring if the cache is available. If the cache constructed fails will return empty. See [Cached](broken-reference)                                                                                                                                                                                                                                                       |                                                                                                                                                        |
|    deployStatus   | L1 ERC1155 NFT contract deploy status                                                                                                                                                                                                                                                                                                                                                                                     | "NOT\_DEPLOYED" or "DEPLOY\_FAILED" or "DEPLOYING" or "DEPLOYED"                                                                                       |
|      nftType      | Collections created from loopring.io are all ERC1155                                                                                                                                                                                                                                                                                                                                                                      | "ERC1155" or "ERC721"                                                                                                                                  |
|      isPublic     |                                                                                                                                                                                                                                                                                                                                                                                                                           | false                                                                                                                                                  |
|       times       | See [Times](broken-reference)                                                                                                                                                                                                                                                                                                                                                                                             |                                                                                                                                                        |
|       extra       | See [Extra](broken-reference)                                                                                                                                                                                                                                                                                                                                                                                             |                                                                                                                                                        |
|       count       | How many kinds of nfts user hold under this collection                                                                                                                                                                                                                                                                                                                                                                    | 10                                                                                                                                                     |

#### **Cached**

|   Field   | Description | Example                                                                                                            |
| :-------: | ----------- | ------------------------------------------------------------------------------------------------------------------ |
|   avatar  |             | "https://d12jj0pnkw1mbj.cloudfront.net/088010b1d3ab60069e87a7055554f012eb82d55b4dc88ea7a9a197d89964bc46-original"  |
|   banner  |             | "https://d12jj0pnkw1mbj.cloudfront.net/088010b1d3ab60069e87a7055554f012eb82d55b4dc88ea7a9a197d89964bc46-original", |
|  tileUri  |             | "https://d12jj0pnkw1mbj.cloudfront.net/088010b1d3ab60069e87a7055554f012eb82d55b4dc88ea7a9a197d89964bc46-original", |
| thumbnail |             | "https://d12jj0pnkw1mbj.cloudfront.net/088010b1d3ab60069e87a7055554f012eb82d55b4dc88ea7a9a197d89964bc46-original"  |

#### **Extra**

|    Field    | Description                             | Example            |
| :---------: | --------------------------------------- | ------------------ |
|  properties | See [Properties](broken-reference)      |                    |
| mintChannel | Where this collection initially created | "UNKNOWN\_CHANNEL" |

**Properties**

|        Field        | Description                                                                                             | Example |
| :-----------------: | ------------------------------------------------------------------------------------------------------- | ------- |
|       isLegacy      | If this collection was created from a legacy NFT token address, see Create collection from legacy NFTs  | false   |
|       isPublic      |                                                                                                         | false   |
| isCounterFactualNFT | Whether the NFT token address was counter-factual                                                       | true    |
|      isMintable     | Whether the user can mint more nfts under this token address                                            | true    |
|      isEditable     | Whether the user can edit collection info                                                               | true    |
|     isDeletable     | User can delete one collection only if he is the creator of that collection and the collection is empty | true    |

#### **Times**

|   Field   | Description                    | Example       |
| :-------: | ------------------------------ | ------------- |
| createdAt | Unix timestamp in milliseconds | 1669188281228 |
| updatedAt | Unix timestamp in milliseconds | 1669188281228 |





## **Example**
