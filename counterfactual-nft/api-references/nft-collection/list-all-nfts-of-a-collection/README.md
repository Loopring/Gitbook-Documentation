---
description: List all NFTs in one collection
---

# List all NFTs of a collection

## Endpoint

```
GET /api/v3/nft/public/collection/items
```



## **Request**

| Query Param | Description                               | Example |
| :---------: | ----------------------------------------- | ------- |
|      id     | Collection Id                             | 1       |
|    limit    | (Optional)                                | 10      |
|    offset   | (Optional)                                | 0       |
|   metadata  | (Optional) Whether return metadata of nft | true    |

##

## **Response**

|     Field     | Description                             | Example |
| :-----------: | --------------------------------------- | ------- |
|    totalNum   |                                         | 100     |
| nftTokenInfos | List\[[NftTokenInfo](broken-reference)] |         |

###

### **NftTokenInfo**

|           Field           | Description                                              | Example                                                                     |
| :-----------------------: | -------------------------------------------------------- | --------------------------------------------------------------------------- |
|          nftData          | The unique hash of this token                            | "0x18ae02f9a5470a8be3a935ddcd14cf51ede1c113fa9dbaf54b9387666018fd44"        |
|           minter          | Minter address                                           | "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",                               |
|          nftType          | 1155 or 721                                              | "ERC1155"                                                                   |
|        tokenAddress       | Contract address on L1                                   | "0x1182fe0f76a1b71b6cad6f293724881cd5619166"                                |
|           nftId           | The hex format of token address defined ERC1155 standard | "0x1076ad78b0f2d6834f49b13fe222ddbd1a82300cae073dd1912189863c41c602"        |
|       creatorFeeBips      | Same as royaltyPercentage                                | 10                                                                          |
|     royaltyPercentage     | Percentage of creator will benefit from the nft trade    | 10                                                                          |
| originalRoyaltyPercentage | Initial royaltyPercentage                                | 10                                                                          |
|           status          | Whethe this nft is valid                                 | true                                                                        |
|         nftFactory        |                                                          | "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",                               |
|          nftOwner         | L2 counterfactual nft's owner is it's minter             | "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22"                                |
|         nftBaseUri        |                                                          | "ipfs://0xffd955c46a3c8f3d6d64d3f8a63fa2b6332a2ae8fe551f9d53cbd7aa69700346" |
|       royaltyAddress      | L2 counterfactual nft's royaltyAddress is it's minter    | "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22"                                |
|       originalMinter      |                                                          | "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22"                                |
|         createdAt         |                                                          | 1669792478241                                                               |
|          metadata         | See [NftMetadata](broken-reference)                      |                                                                             |
|           total           | Original mint amount                                     | 10000                                                                       |

#### **NftMetadata**

|     Field    | Description                                                  | Example                                                                        |
| :----------: | ------------------------------------------------------------ | ------------------------------------------------------------------------------ |
|      uri     |                                                              | ipfs://QmPSvC5SpQYnjKur11Q5BTS9W7SH57o9tDJ2beyfPypLho"                         |
|     base     | See [NftMetadataBase](broken-reference)                      |                                                                                |
|   imageSize  | See [NftImageSize](broken-reference)                         |                                                                                |
|     extra    | See [NftMetadataExtra](broken-reference)                     |                                                                                |
|    status    |                                                              | 1                                                                              |
|    nftType   | 1 is ERC1155                                                 | 1                                                                              |
|    network   | 0 is Ethereum                                                | 0                                                                              |
| tokenAddress |                                                              | "0x1182fe0f76a1b71b6cad6f293724881cd5619166"                                   |
|     nftId    | The decimal format of token address defined ERC1155 standard | "7446690786922567458845946516382225024010719297027912278691859884361574893058" |

#### **NftImageSize**

Different sizes of cached nft image by loopring. If not cached, will return empty.

|   Field  | Description                                                                                                                    | Example                                                                                                                           |
| :------: | ------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- |
|  240-240 | 240\*240 pixel                                                                                                                 | "https://d12jj0pnkw1mbj.cloudfront.net/f9b119b8b85769b008c72c4b1e3892b548346021285debfc6eeffe1c3b2d822f1669792478543-240-240.png" |
|  332-332 | 332\*332 pixel                                                                                                                 | "https://d12jj0pnkw1mbj.cloudfront.net/f9b119b8b85769b008c72c4b1e3892b548346021285debfc6eeffe1c3b2d822f1669792478543-332-332.png" |
| original | "https://d12jj0pnkw1mbj.cloudfront.net/f9b119b8b85769b008c72c4b1e3892b548346021285debfc6eeffe1c3b2d822f1669792478543-original" |                                                                                                                                   |

#### **NftMetadataBase**

This model can refer to [ERC1155](https://eips.ethereum.org/EIPS/eip-1155#metadata) standard for details.

|     Field    | Description                                             | Example |
| :----------: | ------------------------------------------------------- | ------- |
|     name     | "test nft 1"                                            |         |
|   decimals   | `-1` means no decimal data                              | -1      |
|  description | "awfewefas"                                             |         |
|     image    | "ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg" |         |
|  properties  | ""                                                      |         |
| localization | ""                                                      |         |
|   createdAt  | 1669272849183                                           |         |
|   updatedAt  | 1669792478951                                           |         |

#### **NftMetadataExtra**

Extra datas defined by other players

|      Field      | Description | Example |
| :-------------: | ----------- | ------- |
|    imageData    |             |         |
|   externalUrl   |             |         |
|    attributes   |             |         |
| backgroundColor |             |         |
|   animationUrl  |             |         |
|    youtubeUrl   |             |         |
|      minter     |             |         |
