# Sample code

### **Request**

```bash
curl --location --request GET 'http://uat2.loopring.io/api/v3/nft/public/collection?id=59' \
--header 'X-API-KEY: jcTxEZlFrVNkFE9osrr43iC2Qs3FYN34a4gbEPP4IJDj4qiuapd3d4VSMWwtfReo'
```

### **Response**

```json
{
  "id": 59,
  "owner": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
  "name": "im don't know",
  "contractAddress": "0xb59bc7f2f1132908639e16598910aa49a5858e35",
  "collectionAddress": "0xb59bc7f2f1132908639e16598910aa49a5858e35",
  "baseUri": "ipfs://0x61d442626ef238e3b9fa9237687bdf37aa836207c718d87cd51dd8c97d858eb1",
  "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
  "description": "",
  "avatar": "",
  "banner": "",
  "thumbnail": "",
  "tileUri": "ipfs://QmfS4WckWPzn2eNU53zuTM9qYyjUpwWYLKdAywTRenzELq",
  "cached": {
    "avatar": "",
    "banner": "",
    "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/49022d561865100f33f9d409e857fb4ad5a6e856f286b972c16df8d7962bf186-original",
    "thumbnail": ""
  },
  "deployStatus": "DEPLOYED",
  "nftType": "ERC1155",
  "times": {
    "createdAt": 1662032934062,
    "updatedAt": 1662032934062
  },
  "extra": {
    "properties": {
      "isLegacy": false,
      "isPublic": false,
      "isCounterFactualNFT": true,
      "isMintable": true,
      "isEditable": true,
      "isDeletable": false
    },
    "mintChannel": "UNKNOWN_CHANNEL"
  }
}
```
