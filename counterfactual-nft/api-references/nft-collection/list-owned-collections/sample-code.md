# Sample code

### **Request**

```bash
curl --location --request GET 'http://uat2.loopring.io/api/v3/nft/collection?owner=0x3be20a5500a331ef148f1aca64e326cd0b605a4b&isMintable=true' \
--header 'X-API-KEY: jcTxEZlFrVNkFE9osrr43iC2Qs3FYN34a4gbEPP4IJDj4qiuapd3d4VSMWwtfReo'
```

### **Response**

```json
{
  "collections": [
    {
      "collection": {
        "id": 256,
        "owner": "0x3be20a5500a331ef148f1aca64e326cd0b605a4b",
        "name": "test1127",
        "contractAddress": "0x4a71d8b79ab6d9ae89e6709a54e53db9c9e27e49",
        "collectionAddress": "0x4a71d8b79ab6d9ae89e6709a54e53db9c9e27e49",
        "baseUri": "ipfs://0x26ae6d3096348959d033b32ef635b58c0b50d5cb2165debafbb7e6eef783fd9e",
        "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
        "description": "",
        "avatar": "",
        "banner": "",
        "thumbnail": "",
        "tileUri": "ipfs://QmZop7r8RQkB3L9BNfkKsZfY82kTVoPQyaSiZsTeKgTDij",
        "cached": {
          "avatar": "",
          "banner": "",
          "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/088010b1d3ab60069e87a7055554f012eb82d55b4dc88ea7a9a197d89964bc46-original",
          "thumbnail": ""
        },
        "deployStatus": "NOT_DEPLOYED",
        "nftType": "ERC1155",
        "isPublic": false,
        "isCounterFactualNFT": true,
        "isMintable": true,
        "isEditable": true,
        "isDeletable": true,
        "times": {
          "createdAt": 1669188281228,
          "updatedAt": 1669188281228
        },
        "extra": {
          "properties": {
            "isLegacy": false,
            "isPublic": false,
            "isCounterFactualNFT": true,
            "isMintable": true,
            "isEditable": true,
            "isDeletable": true
          },
          "mintChannel": "UNKNOWN_CHANNEL"
        }
      }
    },
    {
      "collection": {
        "id": 167,
        "owner": "0x3be20a5500a331ef148f1aca64e326cd0b605a4b",
        "name": "test new 1018",
        "contractAddress": "0xe9e4882b40465fe134dcdfd0af05aa809d0f4fa0",
        "collectionAddress": "0xe9e4882b40465fe134dcdfd0af05aa809d0f4fa0",
        "baseUri": "ipfs://0xc17c3d2cc20efae1194db48ae0bd7a361fdf9d33cbf9c11f9d312115dc330f54",
        "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
        "description": "awefwef",
        "avatar": "",
        "banner": "",
        "thumbnail": "",
        "tileUri": "ipfs://QmZop7r8RQkB3L9BNfkKsZfY82kTVoPQyaSiZsTeKgTDij",
        "cached": {
          "avatar": "",
          "banner": "",
          "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/088010b1d3ab60069e87a7055554f012eb82d55b4dc88ea7a9a197d89964bc46-original",
          "thumbnail": ""
        },
        "deployStatus": "NOT_DEPLOYED",
        "nftType": "ERC1155",
        "isPublic": false,
        "isCounterFactualNFT": true,
        "isMintable": true,
        "isEditable": true,
        "isDeletable": true,
        "times": {
          "createdAt": 1666072034102,
          "updatedAt": 1666072034102
        },
        "extra": {
          "properties": {
            "isLegacy": false,
            "isPublic": false,
            "isCounterFactualNFT": true,
            "isMintable": true,
            "isEditable": true,
            "isDeletable": true
          },
          "mintChannel": "UNKNOWN_CHANNEL"
        }
      }
    }
  ],
  "totalNum": 20
}
```
