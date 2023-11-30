---
description: Delete collection by id
---

# Delete collection



## Endpoint

```
DELETE /api/v3/nft/collection
```



## Header

|   Field   | Description     | Example                                                                                                                                                                                              |
| :-------: | --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| X-API-KEY | ApiKey          | "HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"                                                                                                                                   |
| X-API-SIG | EDDSA signature | "0x2ed33a593dd8f4676782757f218dbb352e76b425b069deeae5b5afaf89d7dec0090d77da4e548ae46ecf97deb0a2f44f600129d22a9f3817fbeb016446025e6101ec4d2bf04cdcc1a436c8fadf7e809d2d23555b50c6fee6691ab3df62265d7b" |

##

## **Request**

|     Body     | Description                | Example |
| :----------: | -------------------------- | ------- |
|   accountId  | User account Id            | 10001   |
| collectionId | Id of collection to delete | 1       |

##

## **Response**

|  Field | Description | Example |
| :----: | ----------- | ------- |
| result |             | true    |



