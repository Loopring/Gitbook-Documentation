---
description: List user-owned NFTs under one collection
---

# List user's NFTs under one collection



## Endpoint

```
GET /api/v3/user/nft/collection/balances
```



## Header

|   Field   | Description | Example                                                            |
| :-------: | ----------- | ------------------------------------------------------------------ |
| X-API-KEY | ApiKey      | "HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN" |

## **Request**

|     Query Param     | Description                      | Example                                      |
| :-----------------: | -------------------------------- | -------------------------------------------- |
|      accountId      | User AccountId                   | 10083                                        |
|     collectionId    | Which collection to view balance | 11                                           |
|     tokenAddress    | Nft token address                | "0x1cACC96e5F01e2849E6036F25531A9A064D2FB5f" |
|  offset (Optional)  |                                  | 0                                            |
|   limit (Optional)  |                                  | 50                                           |
| metadata (Optional) | Whether return nft metadata      | true                                         |
|  nonZero (Optional) | Only return non-zero nfts        | true                                         |

##

## **Response**

|   Field  | Description                                                           | Example |
| :------: | --------------------------------------------------------------------- | ------- |
| totalNum | Total nft number                                                      | 10      |
|   data   | List\[[NftTokenInfo](../list-all-nfts-of-a-collection/#nfttokeninfo)] |         |



