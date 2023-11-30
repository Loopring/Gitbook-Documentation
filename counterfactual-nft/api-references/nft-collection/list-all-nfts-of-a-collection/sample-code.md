# Sample code

### **Request**

```bash
curl 'https://uat2.loopring.io/api/v3/nft/public/collection/items?id=261&limit=12&metadata=true&offset=0'
```

### **Response**

```json
{
  "totalNum": 3,
  "nftTokenInfos": [
    {
      "nftData": "0x18ae02f9a5470a8be3a935ddcd14cf51ede1c113fa9dbaf54b9387666018fd44",
      "minter": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
      "nftType": "ERC1155",
      "tokenAddress": "0x1182fe0f76a1b71b6cad6f293724881cd5619166",
      "nftId": "0x1076ad78b0f2d6834f49b13fe222ddbd1a82300cae073dd1912189863c41c602",
      "creatorFeeBips": 10,
      "royaltyPercentage": 10,
      "originalRoyaltyPercentage": 10,
      "status": true,
      "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
      "nftOwner": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
      "nftBaseUri": "ipfs://0xffd955c46a3c8f3d6d64d3f8a63fa2b6332a2ae8fe551f9d53cbd7aa69700346",
      "royaltyAddress": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
      "originalMinter": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
      "createdAt": 1669792478241,
      "metadata": {
        "uri": "ipfs://QmPSvC5SpQYnjKur11Q5BTS9W7SH57o9tDJ2beyfPypLho",
        "base": {
          "name": "afwaefsdfg",
          "decimals": -1,
          "description": "awfewefas",
          "image": "ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
          "properties": "",
          "localization": "",
          "createdAt": 1669272849183,
          "updatedAt": 1669792478951
        },
        "imageSize": {
          "240-240": "https://d12jj0pnkw1mbj.cloudfront.net/f9b119b8b85769b008c72c4b1e3892b548346021285debfc6eeffe1c3b2d822f1669792478543-240-240.png",
          "332-332": "https://d12jj0pnkw1mbj.cloudfront.net/f9b119b8b85769b008c72c4b1e3892b548346021285debfc6eeffe1c3b2d822f1669792478543-332-332.png",
          "original": "https://d12jj0pnkw1mbj.cloudfront.net/f9b119b8b85769b008c72c4b1e3892b548346021285debfc6eeffe1c3b2d822f1669792478543-original"
        },
        "extra": {
          "imageData": "",
          "externalUrl": "",
          "attributes": "",
          "backgroundColor": "",
          "animationUrl": "",
          "youtubeUrl": "",
          "minter": ""
        },
        "status": 1,
        "nftType": 1,
        "network": 0,
        "tokenAddress": "0x1182fe0f76a1b71b6cad6f293724881cd5619166",
        "nftId": "7446690786922567458845946516382225024010719297027912278691859884361574893058"
      },
      "total": 0
    },
    {
      "nftData": "0x0c8376a5550f47a39f636f0adc169698993120f99696b556f2de47026c6acb5b",
      "minter": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
      "nftType": "ERC1155",
      "tokenAddress": "0x1182fe0f76a1b71b6cad6f293724881cd5619166",
      "nftId": "0xbead487f48dc4696a59236bcfa1474d16e681ed8f24cb38c8e237f19b042e38f",
      "creatorFeeBips": 10,
      "royaltyPercentage": 10,
      "originalRoyaltyPercentage": 10,
      "status": true,
      "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
      "nftOwner": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
      "nftBaseUri": "ipfs://0xffd955c46a3c8f3d6d64d3f8a63fa2b6332a2ae8fe551f9d53cbd7aa69700346",
      "royaltyAddress": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
      "originalMinter": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
      "createdAt": 1669280387724,
      "metadata": {
        "uri": "ipfs://QmbAyRamCLU3GBJZHttMfyo4Pi16oo8Ht1n8soD5wgjz8v",
        "base": {
          "name": "awefsdgdrsg",
          "decimals": -1,
          "description": "awefasdzgge ",
          "image": "ipfs://QmQU13nHCxHhKRopqUiRN6wuvhEWGieemUPbJQ4k8cADuo",
          "properties": "",
          "localization": "",
          "createdAt": 1669280534037,
          "updatedAt": 1669280534651
        },
        "imageSize": {
          "240-240": "https://d12jj0pnkw1mbj.cloudfront.net/ad237aa59f445741c94cbbb62e9b57f8cb6ee3c9747c21010885a466cbfade011669280534129-240-240.png",
          "332-332": "https://d12jj0pnkw1mbj.cloudfront.net/ad237aa59f445741c94cbbb62e9b57f8cb6ee3c9747c21010885a466cbfade011669280534129-332-332.png",
          "original": "https://d12jj0pnkw1mbj.cloudfront.net/ad237aa59f445741c94cbbb62e9b57f8cb6ee3c9747c21010885a466cbfade011669280534129-original"
        },
        "extra": {
          "imageData": "",
          "externalUrl": "",
          "attributes": "",
          "backgroundColor": "",
          "animationUrl": "",
          "youtubeUrl": "",
          "minter": ""
        },
        "status": 1,
        "nftType": 1,
        "network": 0,
        "tokenAddress": "0x1182fe0f76a1b71b6cad6f293724881cd5619166",
        "nftId": "86245606130350571110750385070472099307803561163807055516290590299152625886095"
      },
      "total": 89898
    },
    {
      "nftData": "0x1026aa9363af390bbf8bf770895e68fe4203fff2e786949aa31437029f410098",
      "minter": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
      "nftType": "ERC1155",
      "tokenAddress": "0x1182fe0f76a1b71b6cad6f293724881cd5619166",
      "nftId": "0x1076ad78b0f2d6834f49b13fe222ddbd1a82300cae073dd1912189863c41c602",
      "creatorFeeBips": 10,
      "royaltyPercentage": 10,
      "originalRoyaltyPercentage": 10,
      "status": true,
      "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
      "nftOwner": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
      "nftBaseUri": "ipfs://0xffd955c46a3c8f3d6d64d3f8a63fa2b6332a2ae8fe551f9d53cbd7aa69700346",
      "royaltyAddress": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
      "originalMinter": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
      "createdAt": 1669272683846,
      "metadata": {
        "uri": "ipfs://QmPSvC5SpQYnjKur11Q5BTS9W7SH57o9tDJ2beyfPypLho",
        "base": {
          "name": "zsfdgerhehjx",
          "decimals": -1,
          "description": "szdfewgg",
          "image": "ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
          "properties": "",
          "localization": "",
          "createdAt": 1669272849183,
          "updatedAt": 1669792478951
        },
        "imageSize": {
          "240-240": "https://d12jj0pnkw1mbj.cloudfront.net/f9b119b8b85769b008c72c4b1e3892b548346021285debfc6eeffe1c3b2d822f1669792478543-240-240.png",
          "332-332": "https://d12jj0pnkw1mbj.cloudfront.net/f9b119b8b85769b008c72c4b1e3892b548346021285debfc6eeffe1c3b2d822f1669792478543-332-332.png",
          "original": "https://d12jj0pnkw1mbj.cloudfront.net/f9b119b8b85769b008c72c4b1e3892b548346021285debfc6eeffe1c3b2d822f1669792478543-original"
        },
        "extra": {
          "imageData": "",
          "externalUrl": "",
          "attributes": "",
          "backgroundColor": "",
          "animationUrl": "",
          "youtubeUrl": "",
          "minter": ""
        },
        "status": 1,
        "nftType": 1,
        "network": 0,
        "tokenAddress": "0x1182fe0f76a1b71b6cad6f293724881cd5619166",
        "nftId": "7446690786922567458845946516382225024010719297027912278691859884361574893058"
      },
      "total": 232
    }
  ]
}
```
