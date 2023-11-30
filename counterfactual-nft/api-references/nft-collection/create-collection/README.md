---
description: Create an empty collection and return a tokenAddress
---

# Create collection

## Endpoint

```
POST /api/v3/nft/collection
```



## Header

|   Field   | Description     | Example                                                                                                                                                                                              |
| :-------: | --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| X-API-KEY | ApiKey          | "HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"                                                                                                                                   |
| X-API-SIG | EDDSA signature | "0x2ed33a593dd8f4676782757f218dbb352e76b425b069deeae5b5afaf89d7dec0090d77da4e548ae46ecf97deb0a2f44f600129d22a9f3817fbeb016446025e6101ec4d2bf04cdcc1a436c8fadf7e809d2d23555b50c6fee6691ab3df62265d7b" |

##

## **Request**

|     Body    | Description                                                                                                                                                                                                                                                                             | Example                                                                                                           |
| :---------: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
|    owner    | Address of creator                                                                                                                                                                                                                                                                      | "0x1cACC96e5F01e2849E6036F25531A9A064D2FB5f"                                                                      |
|     name    | The name of the collection, each owner can not use the same collection name more than once.                                                                                                                                                                                             | "test"                                                                                                            |
|  nftFactory | Address of nftFactory contract, nftFactory is a contract which will generate ERC1155 contract on L1 once L2 nfts withdrawn. Latest nftFactory contract deployed on **Ethereum**:`0x97BE94250AEF1Df307749aFAeD27f9bc8aB911db`,on **Goerli**:`0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281` | "0x97BE94250AEF1Df307749aFAeD27f9bc8aB911db"                                                                      |
|   tileUri   | The URI of the collection tile image, should start with `ipfs://` or `https://` or `http://`                                                                                                                                                                                            | "ipfs://QmfS4WckWPzn2eNU53zuTM9qYyjUpwWYLKdAywTRenzELq"                                                           |
| description | (Optional) Description text of collection                                                                                                                                                                                                                                               | "This is the description of my collection, amazing 😍"                                                            |
|    avatar   | The URI of the collection avatar image should start with `ipfs://` or `https://` or `http://`                                                                                                                                                                                           | "ipfs://QmZop7r8RQkB3L9BNfkKsZfY82kTVoPQyaSiZsTeKgTDij"                                                           |
|    banner   | (Optional) The URI of the collection banner image, should start with `ipfs://` or `https://` or `http://`                                                                                                                                                                               | "https://d12jj0pnkw1mbj.cloudfront.net/088010b1d3ab60069e87a7055554f012eb82d55b4dc88ea7a9a197d89964bc46-original" |
|  thumbnail  | (Optional) The URI of the collection thumbnail image, should start with `ipfs://` or `https://` or `http://`                                                                                                                                                                            | "ipfs://QmfS4WckWPzn2eNU53zuTM9qYyjUpwWYLKdAywTRenzELq"                                                           |
|   network   | (Optional) Blockchain network of the collection, default is `ETHEREUM`, this field in the most situation can be omitted                                                                                                                                                                 | "ETHEREUM"                                                                                                        |

##

## **Response**

|      Field      | Description   | Example                                      |
| :-------------: | ------------- | -------------------------------------------- |
| contractAddress | Token address | "0x4a71d8b79ab6d9ae89e6709a54e53db9c9e27e49" |
