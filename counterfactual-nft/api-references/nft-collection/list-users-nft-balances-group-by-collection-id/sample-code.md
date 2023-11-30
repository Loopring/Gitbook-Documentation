# Sample code

### **Request**

```bash
curl 'https://uat2.loopring.io/api/v3/user/collection/details?accountId=17608&limit=12&offset=0' \
  -H 'X-API-KEY: DuuMSExGhJmfqWlxyRQMDVkARW1V9RmvrZEoyl8JZ0DkZ08up291ckGNuLigvVox' \
  --compressed
```

### **Response**

```json
{
  "collections": [
    {
      "collection": {
        "id": 254,
        "owner": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
        "name": "理科生发牢骚",
        "contractAddress": "0x1abe8e24312e9fe614b5c9c67b472b3ecb3b8788",
        "collectionAddress": "0x1abe8e24312e9fe614b5c9c67b472b3ecb3b8788",
        "baseUri": "ipfs://0x468bbfd8f2ac40a0d71a67b76af348d318e7ac0009f686b273758717888a5674",
        "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
        "description": "水电费路上的风景",
        "avatar": "ipfs://QmUmG1TkJEfJ8AgvmoydpZRacB66ChGMCn5hkj6i2uuxvs",
        "banner": "ipfs://QmUmG1TkJEfJ8AgvmoydpZRacB66ChGMCn5hkj6i2uuxvs",
        "thumbnail": "",
        "tileUri": "ipfs://QmUmG1TkJEfJ8AgvmoydpZRacB66ChGMCn5hkj6i2uuxvs",
        "cached": {
          "avatar": "https://d12jj0pnkw1mbj.cloudfront.net/16ccbc51fb02ce67b668f8187cc0f46fe8ac2e356b75ca24dfbd34249a339861-original",
          "banner": "https://d12jj0pnkw1mbj.cloudfront.net/16ccbc51fb02ce67b668f8187cc0f46fe8ac2e356b75ca24dfbd34249a339861-original",
          "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/16ccbc51fb02ce67b668f8187cc0f46fe8ac2e356b75ca24dfbd34249a339861-original",
          "thumbnail": ""
        },
        "deployStatus": "DEPLOYED",
        "nftType": "ERC1155",
        "times": {
          "createdAt": 1669109427624,
          "updatedAt": 1669109427624
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
      },
      "count": 2
    },
    {
      "collection": {
        "id": 235,
        "owner": "0xff7d59d9316eba168837e3ef924bcdfd64b237d8",
        "name": "import时创建collection，嗯对的，你好啊世",
        "contractAddress": "0x1c0dcacface2ed152b2d232c01cfd725dd6cf4be",
        "collectionAddress": "0x1c0dcacface2ed152b2d232c01cfd725dd6cf4be-0x9021527c5bd0575c62d4ce8e3b0bbdd7413929784011bfb4916088d29aed4305",
        "baseUri": "",
        "nftFactory": "0x25315F9878BA07221db684b7ad3676502E914894",
        "description": "如标题描述\nthis\n哈哈\n这是啥",
        "avatar": "ipfs://QmQvvVRgBKBszZkTdNmJdk8KaoLuifPSzaoWS5oSvznmNU",
        "banner": "ipfs://QmQvvVRgBKBszZkTdNmJdk8KaoLuifPSzaoWS5oSvznmNU",
        "thumbnail": "",
        "tileUri": "ipfs://QmQvvVRgBKBszZkTdNmJdk8KaoLuifPSzaoWS5oSvznmNU",
        "cached": {
          "avatar": "https://d12jj0pnkw1mbj.cloudfront.net/f99a114a765d1bd5e9f700d4719e39b50b000a962cf1167ea9d454faf7fb3c43-original",
          "banner": "https://d12jj0pnkw1mbj.cloudfront.net/f99a114a765d1bd5e9f700d4719e39b50b000a962cf1167ea9d454faf7fb3c43-original",
          "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/f99a114a765d1bd5e9f700d4719e39b50b000a962cf1167ea9d454faf7fb3c43-original",
          "thumbnail": ""
        },
        "deployStatus": "DEPLOYED",
        "nftType": "ERC1155",
        "times": {
          "createdAt": 1668063875766,
          "updatedAt": 1668063875766
        },
        "extra": {
          "properties": {
            "isLegacy": true,
            "isPublic": false,
            "isCounterFactualNFT": true,
            "isMintable": false,
            "isEditable": true,
            "isDeletable": false
          },
          "mintChannel": "UNKNOWN_CHANNEL"
        }
      },
      "count": 1
    },
    {
      "collection": {
        "id": 267,
        "owner": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
        "name": "就开始地方是",
        "contractAddress": "0x66d74d70e20e3de7fd72b5ded84db24df9733413",
        "collectionAddress": "0x66d74d70e20e3de7fd72b5ded84db24df9733413",
        "baseUri": "ipfs://0xd1833ab706dba611e7eb5abe555eab7dd3881193df5db01867c6bd8ed56655f2",
        "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
        "description": "撒地方洛杉矶地方",
        "avatar": "ipfs://QmUmG1TkJEfJ8AgvmoydpZRacB66ChGMCn5hkj6i2uuxvs",
        "banner": "ipfs://QmUmG1TkJEfJ8AgvmoydpZRacB66ChGMCn5hkj6i2uuxvs",
        "thumbnail": "",
        "tileUri": "ipfs://QmUmG1TkJEfJ8AgvmoydpZRacB66ChGMCn5hkj6i2uuxvs",
        "cached": {
          "avatar": "https://d12jj0pnkw1mbj.cloudfront.net/16ccbc51fb02ce67b668f8187cc0f46fe8ac2e356b75ca24dfbd34249a339861-original",
          "banner": "https://d12jj0pnkw1mbj.cloudfront.net/16ccbc51fb02ce67b668f8187cc0f46fe8ac2e356b75ca24dfbd34249a339861-original",
          "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/16ccbc51fb02ce67b668f8187cc0f46fe8ac2e356b75ca24dfbd34249a339861-original",
          "thumbnail": ""
        },
        "deployStatus": "NOT_DEPLOYED",
        "nftType": "ERC1155",
        "times": {
          "createdAt": 1669291877234,
          "updatedAt": 1669291877234
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
      },
      "count": 3
    },
    {
      "collection": {
        "id": 249,
        "owner": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
        "name": "好",
        "contractAddress": "0xfbcc5e1c1cec9a7febe39f0556c4c8f0bcff6849",
        "collectionAddress": "0xfbcc5e1c1cec9a7febe39f0556c4c8f0bcff6849",
        "baseUri": "ipfs://0x9d9e8784c3dcd9af70164c75e7b6dd97cffc17627a49567d0f65b519aa7bc0fb",
        "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
        "description": "",
        "avatar": "ipfs://QmWWnkcMV8V2aTnUuAFVBPeRNr9qnkF7GupHUgh7NFxXBy",
        "banner": "ipfs://QmWWnkcMV8V2aTnUuAFVBPeRNr9qnkF7GupHUgh7NFxXBy",
        "thumbnail": "",
        "tileUri": "ipfs://QmWWnkcMV8V2aTnUuAFVBPeRNr9qnkF7GupHUgh7NFxXBy",
        "cached": {
          "avatar": "https://d12jj0pnkw1mbj.cloudfront.net/76f561ef79b798ce34674cce4cce1160fcd0da5fd2197d4c58054e329fc2756c-original",
          "banner": "https://d12jj0pnkw1mbj.cloudfront.net/76f561ef79b798ce34674cce4cce1160fcd0da5fd2197d4c58054e329fc2756c-original",
          "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/76f561ef79b798ce34674cce4cce1160fcd0da5fd2197d4c58054e329fc2756c-original",
          "thumbnail": ""
        },
        "deployStatus": "DEPLOYING",
        "nftType": "ERC1155",
        "times": {
          "createdAt": 1669104573553,
          "updatedAt": 1669104573553
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
      },
      "count": 1
    },
    {
      "collection": {
        "id": 32,
        "owner": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
        "name": "GIF 测试",
        "contractAddress": "0x5209ceb5f36e3ce82fe716ea560ac03d8e8ffc8b",
        "collectionAddress": "0x5209ceb5f36e3ce82fe716ea560ac03d8e8ffc8b",
        "baseUri": "ipfs://0x160704909985cb8175c6df5823cc4cb91198b43f73ca8edc8cdf15f22f365cbf",
        "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
        "description": "这是一个GIF集合",
        "avatar": "",
        "banner": "",
        "thumbnail": "",
        "tileUri": "ipfs://QmRfjAjocGJyX33QLzcJbUkoE5RfuLdyUYVv9dA4iAXeaM",
        "cached": {
          "avatar": "",
          "banner": "",
          "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/a5615f78e9be152428adb0f7bd7813646a7a742ffdd593f15da7af84b31b4481-original",
          "thumbnail": ""
        },
        "deployStatus": "NOT_DEPLOYED",
        "nftType": "ERC1155",
        "times": {
          "createdAt": 1661824119053,
          "updatedAt": 1661824119053
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
      },
      "count": 2
    },
    {
      "collection": {
        "id": 250,
        "owner": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
        "name": "撒地方",
        "contractAddress": "0x3111983f5457309e17d4adc6d8950fe7e0e0f9de",
        "collectionAddress": "0x3111983f5457309e17d4adc6d8950fe7e0e0f9de",
        "baseUri": "ipfs://0x1befa50095b2ba05ef2c6626ea7d3ec0d8640a6ba5f1d4c2d3d6121fe9e8c500",
        "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
        "description": "短发短发",
        "avatar": "ipfs://QmQKxcPYUGkKSVamnD6LekSdNutWGmSy8TW5HEsM1xbupS",
        "banner": "ipfs://QmQKxcPYUGkKSVamnD6LekSdNutWGmSy8TW5HEsM1xbupS",
        "thumbnail": "",
        "tileUri": "ipfs://QmQKxcPYUGkKSVamnD6LekSdNutWGmSy8TW5HEsM1xbupS",
        "cached": {
          "avatar": "https://d12jj0pnkw1mbj.cloudfront.net/02c4fbe404295411ab8ada65630028acdfd92646f11db522faa8dd9c2ecc60b0-original",
          "banner": "https://d12jj0pnkw1mbj.cloudfront.net/02c4fbe404295411ab8ada65630028acdfd92646f11db522faa8dd9c2ecc60b0-original",
          "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/02c4fbe404295411ab8ada65630028acdfd92646f11db522faa8dd9c2ecc60b0-original",
          "thumbnail": ""
        },
        "deployStatus": "DEPLOYING",
        "nftType": "ERC1155",
        "times": {
          "createdAt": 1669105736452,
          "updatedAt": 1669105736452
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
      },
      "count": 1
    },
    {
      "collection": {
        "id": 243,
        "owner": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
        "name": "55555",
        "contractAddress": "0x809c6cf4ba084f425ad61f7002afe8a177fff95b",
        "collectionAddress": "0x809c6cf4ba084f425ad61f7002afe8a177fff95b-0x365b4652e3da13d3549894b07b461e9380765a5620f12dc55cc170c18d836a46",
        "baseUri": "",
        "nftFactory": "0x25315F9878BA07221db684b7ad3676502E914894",
        "description": "",
        "avatar": "",
        "banner": "",
        "thumbnail": "",
        "tileUri": "ipfs://QmaMvmFYtZ3y3Xoq2rggdu1ZCDvBYq26WZ3cLzbZQgwQYJ",
        "cached": {
          "avatar": "",
          "banner": "",
          "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/5bc4080925d7d4b302df45eff9026fa4a9c8922723801a2a0068fc7c75bed4c5-original",
          "thumbnail": ""
        },
        "deployStatus": "NOT_DEPLOYED",
        "nftType": "ERC1155",
        "times": {
          "createdAt": 1668159656766,
          "updatedAt": 1668159656766
        },
        "extra": {
          "properties": {
            "isLegacy": true,
            "isPublic": false,
            "isCounterFactualNFT": true,
            "isMintable": false,
            "isEditable": true,
            "isDeletable": false
          },
          "mintChannel": "UNKNOWN_CHANNEL"
        }
      },
      "count": 1
    },
    {
      "collection": {
        "id": 96,
        "owner": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
        "name": "beautiful girl",
        "contractAddress": "0x36c653d15ee38dcdf606aec24838bad95328608c",
        "collectionAddress": "0x36c653d15ee38dcdf606aec24838bad95328608c",
        "baseUri": "ipfs://0x4117c2e8bcb55ea0bb584f2a238d4fd12b8482bdb253d6be86865a2955350508",
        "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
        "description": "哈哈哈哈",
        "avatar": "ipfs://QmRzTUysJzHNubbiyWdT5PWBLBfc3MY5ru446Ga7wdJGCC",
        "banner": "ipfs://QmWzsdF5Ey13EDH9EFS14mZ6WyYpXxhQm3hATAkSHAmU1Z",
        "thumbnail": "",
        "tileUri": "ipfs://QmUoAR8tFgm5yA2JrZrsAkgBgTfnGXpZREWfYmuGoX3pHt",
        "cached": {
          "avatar": "https://d12jj0pnkw1mbj.cloudfront.net/394411b80129e7a23333c379f8f81abe45d73d3190fe711dec78ffc272924413-original",
          "banner": "https://d12jj0pnkw1mbj.cloudfront.net/25b41f032cfd84f14f33f7d3273dcc62efb9d4e4520c8b7e301566f40ee5de5d-original",
          "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/5c032023c5da525e4d71293996f1bac4c725505f50b430ae9786dd4e61a76631-original",
          "thumbnail": ""
        },
        "deployStatus": "DEPLOYED",
        "nftType": "ERC1155",
        "times": {
          "createdAt": 1663864412809,
          "updatedAt": 1663864412809
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
      },
      "count": 1
    },
    {
      "collection": {
        "id": 261,
        "owner": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
        "name": "new name 123",
        "contractAddress": "0x1182fe0f76a1b71b6cad6f293724881cd5619166",
        "collectionAddress": "0x1182fe0f76a1b71b6cad6f293724881cd5619166",
        "baseUri": "ipfs://0xffd955c46a3c8f3d6d64d3f8a63fa2b6332a2ae8fe551f9d53cbd7aa69700346",
        "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
        "description": "afweafawfwe new desc",
        "avatar": "ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
        "banner": "ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
        "thumbnail": "",
        "tileUri": "ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
        "cached": {
          "avatar": "https://d12jj0pnkw1mbj.cloudfront.net/4bdaaff74ee8011fe50609ff9788d75627e8e8a9c198c49821ad9826c10e456c-original",
          "banner": "https://d12jj0pnkw1mbj.cloudfront.net/4bdaaff74ee8011fe50609ff9788d75627e8e8a9c198c49821ad9826c10e456c-original",
          "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/4bdaaff74ee8011fe50609ff9788d75627e8e8a9c198c49821ad9826c10e456c-original",
          "thumbnail": ""
        },
        "deployStatus": "DEPLOYED",
        "nftType": "ERC1155",
        "times": {
          "createdAt": 1669262610537,
          "updatedAt": 1669262610537
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
      },
      "count": 2
    },
    {
      "collection": {
        "id": 278,
        "owner": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
        "name": "设计地方上的浪费",
        "contractAddress": "0x1ef89ceac246303d75aee5ae22b6517c3527515d",
        "collectionAddress": "0x1ef89ceac246303d75aee5ae22b6517c3527515d",
        "baseUri": "ipfs://0x162a23c70e1058779b8e9b99fe3632d00a9c723a310f87a4c121ab9b385a31ca",
        "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
        "description": "见识到；副科级啊撒地方",
        "avatar": "ipfs://QmUuiVCNrXg4CLcVf7GBrHiahArHtcpCrJZViKLRqcNLSH",
        "banner": "ipfs://QmPJmHYgWkFoKE9btZv2WKe9XEnMuMgLRyQrvi6zuW4Knq",
        "thumbnail": "",
        "tileUri": "ipfs://QmTVvEJXD8SPEmDmVgFu5MSGZo8BNopEZnGr29RVHz6SjM",
        "cached": {
          "avatar": "https://d12jj0pnkw1mbj.cloudfront.net/4d53439a9694aca1e50a01837de934d1dfe349ac3e6d8eb928f83bd9d1989dca-original",
          "banner": "https://d12jj0pnkw1mbj.cloudfront.net/0141eab77ebe5228537bef2b43293f169c9ad2e15be688de019327463a469af9-original",
          "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/787274c8c55de739cfdaf69866d2f1ad0a24c423756c3ec236cbd355a7e6bfc5-original",
          "thumbnail": ""
        },
        "deployStatus": "DEPLOYED",
        "nftType": "ERC1155",
        "times": {
          "createdAt": 1669791871536,
          "updatedAt": 1669791871536
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
      },
      "count": 2
    },
    {
      "collection": {
        "id": 209,
        "owner": "0xff7d59d9316eba168837e3ef924bcdfd64b237d8",
        "name": "xxx",
        "contractAddress": "0x1c0dcacface2ed152b2d232c01cfd725dd6cf4be",
        "collectionAddress": "0x1c0dcacface2ed152b2d232c01cfd725dd6cf4be-0x247826f7e0a23cdbb524584b2badb571fceac4a584ca8dd79334ba089640d835",
        "baseUri": "",
        "nftFactory": "0x25315F9878BA07221db684b7ad3676502E914894",
        "description": "",
        "avatar": "",
        "banner": "",
        "thumbnail": "",
        "tileUri": "ipfs://Qmc7uigbUtGCbk1RAmAvnEvgt2c6CHjYXDdAx4Hg7FFyaS",
        "cached": {
          "avatar": "",
          "banner": "",
          "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/7e564848ee74d43d64d314e8ff575d7a645ac31ad97547200b61214d4d353f16-original",
          "thumbnail": ""
        },
        "deployStatus": "DEPLOYED",
        "nftType": "ERC1155",
        "times": {
          "createdAt": 1666958444466,
          "updatedAt": 1666958444466
        },
        "extra": {
          "properties": {
            "isLegacy": true,
            "isPublic": false,
            "isCounterFactualNFT": true,
            "isMintable": false,
            "isEditable": true,
            "isDeletable": false
          },
          "mintChannel": "UNKNOWN_CHANNEL"
        }
      },
      "count": 1
    },
    {
      "collection": {
        "id": 71,
        "owner": "0xB4A0C11E4d0D434bb4E9A133E5a6B7B058530e22",
        "name": "test fee",
        "contractAddress": "0x038d2650e3dd2a2908272b6dda19e72830139ede",
        "collectionAddress": "0x038d2650e3dd2a2908272b6dda19e72830139ede",
        "baseUri": "ipfs://0xb183479b3d9f1b24469f29ec979e283bc332c924636624887e190cf2dc70b8f5",
        "nftFactory": "0xfDDA90dbCc99B3a91e3fB1292991Ba1076d9E281",
        "description": "",
        "avatar": "ipfs://QmfSRwvhShpfDc8T3hgbRafx6u1XNHzGuaGCMWK2UTnSHn",
        "banner": "",
        "thumbnail": "",
        "tileUri": "ipfs://QmZ5v9Zvuy9LwoJgTV2YRtrutRghe2uERr6JEdXQMzsho9",
        "cached": {
          "avatar": "https://d12jj0pnkw1mbj.cloudfront.net/2558aeba3fd855e1870b1a90efa41f99426d3fd4e1657d992995b4f7d26c9fb9-original",
          "banner": "",
          "tileUri": "https://d12jj0pnkw1mbj.cloudfront.net/3b7a58636d0f68049483d47863897b759c243fa6d58939333298b00b3fffd86a-original",
          "thumbnail": ""
        },
        "deployStatus": "DEPLOYED",
        "nftType": "ERC1155",
        "times": {
          "createdAt": 1662105840504,
          "updatedAt": 1662105840504
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
      },
      "count": 3
    }
  ],
  "totalNum": 35
}
```
