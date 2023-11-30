# Sample code

**Request**

```bash
curl --location --request GET 'https://api3.loopring.io/api/v3/nft/public/collections?contractAddress=0xf513f716f7a2902222622aa0bAA1B0017bAC890C'
```

### **esponse**

```json
{
    "collections": [
        {
            "collection": {
                "id": 934,
                "owner": "0x8436e3057b2059374ba94b216576a35c4a76deb2",
                "name": "Metanaut Holi Collection",
                "contractAddress": "0xf513f716f7a2902222622aa0baa1b0017bac890c",
                "collectionAddress": "https://api.nft.gamestop.com/getCollectionMetadata?collectionId=43a49464-c47d-44c3-b165-ea68c310773a",
                "baseUri": "",
                "nftFactory": "",
                "description": "Based on the Holi festival, also known the Festival of Colours or Love, this limited to 100 unique 1 of 1 Metanauts collection will spark some light on your wallet\n",
                "avatar": "https://static.gstop-content.com/65319438-71f4-4dd9-8b4a-ce6bbe21e694",
                "banner": "https://static.gstop-content.com/2af2fc86-5de1-4e83-99e3-1f1f5382979e",
                "thumbnail": "https://static.gstop-content.com/ca5408e1-7f8b-4195-ac2b-076589efacac",
                "tileUri": "https://static.gstop-content.com/6d7329ce-99f7-4677-9f44-291d43e70f45",
                "cached": {
                    "avatar": "https://d2y691019xyzhi.cloudfront.net/746b25186bb1b16e377998b02d8c3b1eab0db35b747b7be5409c3163c46ac029-original",
                    "banner": "https://d2y691019xyzhi.cloudfront.net/0748bc64738b5cf75b9b8987f0da93e05c04211fe85c083f389a953e39398592-original",
                    "tileUri": "https://d2y691019xyzhi.cloudfront.net/2b402f6e375b06c2b29e22f602c2e28972a9130f833cb48035d19b0557baeb05-original",
                    "thumbnail": "https://d2y691019xyzhi.cloudfront.net/423fd1c7ab713b7c707ee75fa8b300e82d19c51db0d6f190493627ca02025116-original"
                },
                "deployStatus": "DEPLOYED",
                "nftType": "ERC1155",
                "times": {
                    "createdAt": 1665098570787,
                    "updatedAt": 1684103323471
                },
                "extra": {
                    "properties": {
                        "isLegacy": false,
                        "isPublic": false,
                        "isCounterFactualNFT": true,
                        "isMintable": false,
                        "isEditable": false,
                        "isDeletable": false
                    },
                    "mintChannel": "GME"
                }
            }
        },
        {
            "collection": {
                "id": 1047,
                "owner": "0x8436e3057b2059374ba94b216576a35c4a76deb2",
                "name": "USA Collection",
                "contractAddress": "0xf513f716f7a2902222622aa0baa1b0017bac890c",
                "collectionAddress": "https://api.nft.gamestop.com/getCollectionMetadata?collectionId=3c6fa7f0-b277-42f4-aa20-32db0a91437d",
                "baseUri": "",
                "nftFactory": "0xc852aC7aAe4b0f0a0Deb9e8A391ebA2047d80026",
                "description": "Join the club of the metanauts with the limited edition of 10 commemorative USA Metanauts",
                "avatar": "https://static.gstop-content.com/0dd0bf1d-52bf-47f8-91d8-3d44d484c62e",
                "banner": "https://static.gstop-content.com/a7f60889-afae-441a-aa21-7e9cf15bf298",
                "thumbnail": "https://static.gstop-content.com/79230766-bd2f-46fd-8797-7bd3c7d8a394",
                "tileUri": "https://static.gstop-content.com/2ae54371-f6b7-4cc8-9360-8e2cc2ec8347",
                "cached": {
                    "avatar": "https://d2y691019xyzhi.cloudfront.net/c9b4c8d00d37c650f7f2352d782a43d9e67fe0a8ff5c44c64da580127aa6270f-original",
                    "banner": "https://d2y691019xyzhi.cloudfront.net/7e832331810439ec1f3d024ecd4511a3bd4d6886b7bcdf7c6042cb248f0359e7-original",
                    "tileUri": "https://d2y691019xyzhi.cloudfront.net/71bfd7fdce5b0ed69f9c78fd1930d5e8ebf052af9428809f9746cf7a393b6702-original",
                    "thumbnail": "https://d2y691019xyzhi.cloudfront.net/fe8ff0de862577a241d8d5ab86719b9cd7d62c593bc1f2e446b026a8e80cdf19-original"
                },
                "deployStatus": "DEPLOYED",
                "nftType": "ERC1155",
                "times": {
                    "createdAt": 1665442688453,
                    "updatedAt": 1683856224707
                },
                "extra": {
                    "properties": {
                        "isLegacy": true,
                        "isPublic": false,
                        "isCounterFactualNFT": true,
                        "isMintable": false,
                        "isEditable": false,
                        "isDeletable": false
                    },
                    "mintChannel": "GME"
                }
            }
        },
        {
            "collection": {
                "id": 1136,
                "owner": "0x8436e3057b2059374ba94b216576a35c4a76deb2",
                "name": "Minimal Metanaut",
                "contractAddress": "0xf513f716f7a2902222622aa0baa1b0017bac890c",
                "collectionAddress": "https://api.nft.gamestop.com/getCollectionMetadata?collectionId=93716c97-c289-4390-bb61-395826f51763",
                "baseUri": "",
                "nftFactory": "0xc852aC7aAe4b0f0a0Deb9e8A391ebA2047d80026",
                "description": "The new Metanauts",
                "avatar": "https://static.gstop-content.com/daa4f4be-739f-4b5d-99f3-f61d0b0820a9",
                "banner": "https://static.gstop-content.com/14d0d64a-cd66-4fd8-9363-95f545d9c5c5",
                "thumbnail": "https://static.gstop-content.com/002d7da4-0e12-4cb1-b097-2f89caf560ad",
                "tileUri": "https://static.gstop-content.com/0de36dd0-176e-4797-be4e-071ea986a359",
                "cached": {
                    "avatar": "https://d2y691019xyzhi.cloudfront.net/700e5a4d0064c4b0fad8c2462634ec263987d7be583b4d404c5d4f8140f12766-original",
                    "banner": "https://d2y691019xyzhi.cloudfront.net/9b1d82c31a0d30a8e535587203b63a7b2ba1e49803233476b82d9def50c03fef-original",
                    "tileUri": "https://d2y691019xyzhi.cloudfront.net/86f76a50adc57d26ef9b4d2ca8bd92ec1dce6bce73ddef664b775453aed4d78a-original",
                    "thumbnail": "https://d2y691019xyzhi.cloudfront.net/2bf7abfcc7db30c9fc493a3dd8c494788d9669fa8783dc15d6cf4816e498a569-original"
                },
                "deployStatus": "DEPLOYED",
                "nftType": "ERC1155",
                "times": {
                    "createdAt": 1665446117018,
                    "updatedAt": 1683975630749
                },
                "extra": {
                    "properties": {
                        "isLegacy": true,
                        "isPublic": false,
                        "isCounterFactualNFT": true,
                        "isMintable": false,
                        "isEditable": false,
                        "isDeletable": false
                    },
                    "mintChannel": "GME"
                }
            }
        },
        {
            "collection": {
                "id": 5970,
                "owner": "0x8436e3057b2059374ba94b216576a35c4a76deb2",
                "name": "Metanaut .S Collection",
                "contractAddress": "0xf513f716f7a2902222622aa0baa1b0017bac890c",
                "collectionAddress": "0xf513f716f7a2902222622aa0baa1b0017bac890c-0x01353b1647e5db4dfad989f00755ed2452d626857111723130149bd4e6e014ce",
                "baseUri": "",
                "nftFactory": "0xc852aC7aAe4b0f0a0Deb9e8A391ebA2047d80026",
                "description": "",
                "avatar": "ipfs://Qmdtft95drCovVhSJ8Z9wvtX41x2KE1818Kk18SHXh5vjt",
                "banner": "ipfs://QmPxJBXA7XVg86vxrM9AYUFywdBYH4ya6VnnWLYoBQuzwz",
                "thumbnail": "",
                "tileUri": "ipfs://Qmdtft95drCovVhSJ8Z9wvtX41x2KE1818Kk18SHXh5vjt",
                "cached": {
                    "avatar": "https://d2y691019xyzhi.cloudfront.net/64903d7d91f806b9519263023689701f8ffae80c2a2df19413fef06c650433fc-original",
                    "banner": "https://d2y691019xyzhi.cloudfront.net/f5039892c7c6ecc6ebaad155ad48dafa026e28bf65adb435cb1a8eb1bcdd1928-original",
                    "tileUri": "https://d2y691019xyzhi.cloudfront.net/64903d7d91f806b9519263023689701f8ffae80c2a2df19413fef06c650433fc-original",
                    "thumbnail": ""
                },
                "deployStatus": "DEPLOYED",
                "nftType": "ERC1155",
                "times": {
                    "createdAt": 1679991732934,
                    "updatedAt": 1679991732934
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
            }
        },
        {
            "collection": {
                "id": 6070,
                "owner": "0x8436e3057b2059374ba94b216576a35c4a76deb2",
                "name": "Metanaut Origins Collection",
                "contractAddress": "0xf513f716f7a2902222622aa0baa1b0017bac890c",
                "collectionAddress": "0xf513f716f7a2902222622aa0baa1b0017bac890c-0x039cf8cda266fffb4231b94b57abe53676fdca1fbab13c4564445a3202860035",
                "baseUri": "",
                "nftFactory": "0xc852aC7aAe4b0f0a0Deb9e8A391ebA2047d80026",
                "description": "",
                "avatar": "ipfs://QmNTajcMmeuU8mRpfZt5g9tKKPTyPPkfa3o7Eb3Fh8fP5q",
                "banner": "ipfs://QmfQi6YkYnWHWZTUe593TYCw82DAmjMRu4G3gF54hqsxKe",
                "thumbnail": "",
                "tileUri": "ipfs://QmNTajcMmeuU8mRpfZt5g9tKKPTyPPkfa3o7Eb3Fh8fP5q",
                "cached": {
                    "avatar": "https://d2y691019xyzhi.cloudfront.net/1d90af700c77800d9bfc3fe896120499b9efed7416d6f5d9bfa59e9b7354759a-original",
                    "banner": "https://d2y691019xyzhi.cloudfront.net/5bfdda9c8c80e0552871a0703fe6429e7f007d4e70bb536f69a6be59946b9995-original",
                    "tileUri": "https://d2y691019xyzhi.cloudfront.net/1d90af700c77800d9bfc3fe896120499b9efed7416d6f5d9bfa59e9b7354759a-original",
                    "thumbnail": ""
                },
                "deployStatus": "DEPLOYED",
                "nftType": "ERC1155",
                "times": {
                    "createdAt": 1680794475304,
                    "updatedAt": 1680794475304
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
            }
        },
        {
            "collection": {
                "id": 7238,
                "owner": "0x8436e3057b2059374ba94b216576a35c4a76deb2",
                "name": "Metanaut Chameleon",
                "contractAddress": "0xf513f716f7a2902222622aa0baa1b0017bac890c",
                "collectionAddress": "0xf513f716f7a2902222622aa0baa1b0017bac890c-0x08c5d5c1947f68fc5b7f43b6a89c4612668227185395dd6bcd3a264511bbf238",
                "baseUri": "",
                "nftFactory": "0xc852aC7aAe4b0f0a0Deb9e8A391ebA2047d80026",
                "description": "Metanaut Chameleon ˈKamō",
                "avatar": "ipfs://QmfC76EPxMR266U5jgT5LV9gjx77qnNNrSAQASJiRSDwx2",
                "banner": "ipfs://QmbBiua2rc6XZEeaabvAt2eTdXaRPPLkSsKhSyth3V8HUe",
                "thumbnail": "",
                "tileUri": "ipfs://QmfC76EPxMR266U5jgT5LV9gjx77qnNNrSAQASJiRSDwx2",
                "cached": {
                    "avatar": "https://d2y691019xyzhi.cloudfront.net/44da61f26289fad49e57a0226b12d8cf6aef800d7b04dc3708247a06d1ba8e46-original",
                    "banner": "https://d2y691019xyzhi.cloudfront.net/57b5ca5d211b91a17244dc682285ed665d965f70f3df4de99d5e548cac74c3cf-original",
                    "tileUri": "https://d2y691019xyzhi.cloudfront.net/44da61f26289fad49e57a0226b12d8cf6aef800d7b04dc3708247a06d1ba8e46-original",
                    "thumbnail": ""
                },
                "deployStatus": "DEPLOYED",
                "nftType": "ERC1155",
                "times": {
                    "createdAt": 1683542896484,
                    "updatedAt": 1683542896484
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
            }
        },
        {
            "collection": {
                "id": 7239,
                "owner": "0x8436e3057b2059374ba94b216576a35c4a76deb2",
                "name": "Metanaut in Space",
                "contractAddress": "0xf513f716f7a2902222622aa0baa1b0017bac890c",
                "collectionAddress": "0xf513f716f7a2902222622aa0baa1b0017bac890c-0x0ea9e1192ecb6c1f5574bc2731e90d5384f509ef5abd5b45e05820d111f26729",
                "baseUri": "",
                "nftFactory": "0xc852aC7aAe4b0f0a0Deb9e8A391ebA2047d80026",
                "description": "Metanaut in Space",
                "avatar": "ipfs://QmUwW2gP8oKUqYDioqfRstrSxnQLCQ3ou5Xz9xjL7cj4KU",
                "banner": "ipfs://QmbBiua2rc6XZEeaabvAt2eTdXaRPPLkSsKhSyth3V8HUe",
                "thumbnail": "",
                "tileUri": "ipfs://QmUwW2gP8oKUqYDioqfRstrSxnQLCQ3ou5Xz9xjL7cj4KU",
                "cached": {
                    "avatar": "https://d2y691019xyzhi.cloudfront.net/6f5c3299a4c66967523d42cbbf365665bfb90c5233ea37a89949b6a3c3ca4434-original",
                    "banner": "https://d2y691019xyzhi.cloudfront.net/57b5ca5d211b91a17244dc682285ed665d965f70f3df4de99d5e548cac74c3cf-original",
                    "tileUri": "https://d2y691019xyzhi.cloudfront.net/6f5c3299a4c66967523d42cbbf365665bfb90c5233ea37a89949b6a3c3ca4434-original",
                    "thumbnail": ""
                },
                "deployStatus": "DEPLOYED",
                "nftType": "ERC1155",
                "times": {
                    "createdAt": 1683543451163,
                    "updatedAt": 1683543451163
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
            }
        }
    ],
    "totalNum": 7
}
```
