# Sample code

### **Request**

```bash
curl 'https://uat2.loopring.io/api/v3/user/nft/collection/balances?accountId=10032&collectionId=6&favourite=false&hidden=false&limit=12&metadata=true&nonZero=true&offset=0&tokenAddress=0x4727365e03b1284bdcf62eff5c24ba3cfdb13fe1' \
  -H 'X-API-KEY: Mk96fc7e22FlXifH0JUQOzZeWRWJSem4euAykOTJHBgmnG0IN8db1IhghEjzCvRE' \
```

### **Response**

```json
{
   "totalNum":3,
   "data":[
      {
         "id":7,
         "accountId":10032,
         "tokenId":32770,
         "nftData":"0x03e665d11027998228d949e724dd4f7b8c5e098d08fe9f58a1c3c83507ab2846",
         "tokenAddress":"0x4727365e03b1284bdcf62eff5c24ba3cfdb13fe1",
         "nftId":"0x0810e6d238aeee149113ec8ecc3c8307ba9be29719ea5297b0d59697b3d7f27c",
         "nftType":"ERC1155",
         "total":"78000",
         "locked":"0",
         "pending":{
            "withdraw":"0",
            "deposit":"0"
         },
         "deploymentStatus":"DEPLOYED",
         "isCounterFactualNFT":true,
         "metadata":{
            "uri":"ipfs://QmNt8vFqbs4vpyCpVPYcxMVZpke9L7c9q3zyjVEHf471K9",
            "base":{
               "name":"123Matrix Land (13, 72)",
               "decimals":-1,
               "description":"The voucher of a 1x1 Land of Matrix World located at (13, 72)",
               "image":"ipfs://QmYqPLZ73bjqmQZpxrxMUmQs8q2NnRiJHs8D5ArBNuNcyi/0.jpg",
               "properties":"",
               "localization":"",
               "createdAt":1679884925570,
               "updatedAt":1679989336640
            },
            "imageSize":{
               "240-240":"https://d12jj0pnkw1mbj.cloudfront.net/561ee6be0497bc02a0d59d65eff4a9da2b2c278cda7e5089927c58ba9734ccce1679989336257-240-240.png",
               "332-332":"https://d12jj0pnkw1mbj.cloudfront.net/561ee6be0497bc02a0d59d65eff4a9da2b2c278cda7e5089927c58ba9734ccce1679989336257-332-332.png",
               "original":"https://d12jj0pnkw1mbj.cloudfront.net/561ee6be0497bc02a0d59d65eff4a9da2b2c278cda7e5089927c58ba9734ccce1679989336257-original.jpg"
            },
            "extra":{
               "imageData":"",
               "externalUrl":"",
               "attributes":"[{\"value\":\"(13, 72)\",\"trait_type\":\"Position\"},{\"value\":\"1x1\",\"trait_type\":\"Size\"},{\"value\":1,\"trait_type\":\"Area\"}]",
               "backgroundColor":"",
               "animationUrl":"ipfs://QmYJEbZXuC5ihHBneuxm2GQewbjLyaq9DKSxP4geWV1jsa",
               "youtubeUrl":"",
               "minter":""
            },
            "status":1,
            "nftType":1,
            "network":0,
            "tokenAddress":"0x4727365e03b1284bdcf62eff5c24ba3cfdb13fe1",
            "nftId":"0x3648365410920597549601934180836998235594027356918410407389610902518616289916"
         },
         "minter":"0xb4a0c11e4d0d434bb4e9a133e5a6b7b058530e22",
         "royaltyPercentage":0,
         "preference":{
            "favourite":false,
            "hide":false
         },
         "collectionInfo":{
            "id":6,
            "owner":"0xb4a0c11e4d0d434bb4e9a133e5a6b7b058530e22",
            "name":"这是第二个collection",
            "contractAddress":"0x4727365e03b1284bdcf62eff5c24ba3cfdb13fe1",
            "collectionAddress":"0x4727365e03b1284bdcf62eff5c24ba3cfdb13fe1",
            "baseUri":"ipfs://0x0953cd56b04dc347ac8ce67a84c17c90cad33a1e79835456965916499c6fba00",
            "nftFactory":"0x0ad87482a1bfd0B3036Bb4b13708C88ACAe1b8bA",
            "description":"随便上传",
            "avatar":"ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
            "banner":"ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
            "thumbnail":"",
            "tileUri":"ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
            "cached":{
               "avatar":"https://d12jj0pnkw1mbj.cloudfront.net/4bdaaff74ee8011fe50609ff9788d75627e8e8a9c198c49821ad9826c10e456c-original",
               "banner":"https://d12jj0pnkw1mbj.cloudfront.net/4bdaaff74ee8011fe50609ff9788d75627e8e8a9c198c49821ad9826c10e456c-original",
               "tileUri":"https://d12jj0pnkw1mbj.cloudfront.net/4bdaaff74ee8011fe50609ff9788d75627e8e8a9c198c49821ad9826c10e456c-original",
               "thumbnail":""
            },
            "deployStatus":"DEPLOYED",
            "nftType":"ERC1155",
            "times":{
               "createdAt":1679884580731,
               "updatedAt":1679884580731
            },
            "extra":{
               "properties":{
                  "isLegacy":false,
                  "isPublic":false,
                  "isCounterFactualNFT":true,
                  "isMintable":true,
                  "isEditable":true,
                  "isDeletable":false
               },
               "mintChannel":"UNKNOWN_CHANNEL"
            }
         },
         "updatedAt":1679988240788
      },
      {
         "id":6,
         "accountId":10032,
         "tokenId":32769,
         "nftData":"0x19a5de904df6eadc7f197e2a30ea1367d14328ed35de5e58df26ad398c699307",
         "tokenAddress":"0x4727365e03b1284bdcf62eff5c24ba3cfdb13fe1",
         "nftId":"0x85570b55bd8b5b37c3965a31c71a09cab86abd0aa92534c53d9fe63393d28605",
         "nftType":"ERC1155",
         "total":"78000",
         "locked":"0",
         "pending":{
            "withdraw":"0",
            "deposit":"0"
         },
         "deploymentStatus":"DEPLOYED",
         "isCounterFactualNFT":true,
         "metadata":{
            "uri":"ipfs://QmXK9v4oW34Af3YxkxFGiBtKacuHKnJStB3gs1F1f9pBJk",
            "base":{
               "name":"第二个NFT",
               "decimals":-1,
               "description":"这是第二个N FT，不知道啥情况\n哈哈哈\n卡拉斯弗拉索夫\nthis is no",
               "image":"ipfs://QmZ5v9Zvuy9LwoJgTV2YRtrutRghe2uERr6JEdXQMzsho9",
               "properties":"",
               "localization":"",
               "createdAt":1679884925753,
               "updatedAt":1679989739903
            },
            "imageSize":{
               "240-240":"https://d12jj0pnkw1mbj.cloudfront.net/e856683f464fb0e4cef8138c3444fcdeef422cf079170ebdcee223f68598cb501679989739564-240-240.png",
               "332-332":"https://d12jj0pnkw1mbj.cloudfront.net/e856683f464fb0e4cef8138c3444fcdeef422cf079170ebdcee223f68598cb501679989739564-332-332.png",
               "original":"https://d12jj0pnkw1mbj.cloudfront.net/e856683f464fb0e4cef8138c3444fcdeef422cf079170ebdcee223f68598cb501679989739564-original"
            },
            "extra":{
               "imageData":"",
               "externalUrl":"",
               "attributes":"",
               "backgroundColor":"",
               "animationUrl":"ipfs://QmZ5v9Zvuy9LwoJgTV2YRtrutRghe2uERr6JEdXQMzsho9",
               "youtubeUrl":"",
               "minter":""
            },
            "status":1,
            "nftType":1,
            "network":0,
            "tokenAddress":"0x4727365e03b1284bdcf62eff5c24ba3cfdb13fe1",
            "nftId":"0x60311402786976781484454534706069364837650628169017968694905431260135219693061"
         },
         "minter":"0xb4a0c11e4d0d434bb4e9a133e5a6b7b058530e22",
         "royaltyPercentage":8,
         "preference":{
            "favourite":false,
            "hide":false
         },
         "collectionInfo":{
            "id":6,
            "owner":"0xb4a0c11e4d0d434bb4e9a133e5a6b7b058530e22",
            "name":"这是第二个collection",
            "contractAddress":"0x4727365e03b1284bdcf62eff5c24ba3cfdb13fe1",
            "collectionAddress":"0x4727365e03b1284bdcf62eff5c24ba3cfdb13fe1",
            "baseUri":"ipfs://0x0953cd56b04dc347ac8ce67a84c17c90cad33a1e79835456965916499c6fba00",
            "nftFactory":"0x0ad87482a1bfd0B3036Bb4b13708C88ACAe1b8bA",
            "description":"随便上传",
            "avatar":"ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
            "banner":"ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
            "thumbnail":"",
            "tileUri":"ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
            "cached":{
               "avatar":"https://d12jj0pnkw1mbj.cloudfront.net/4bdaaff74ee8011fe50609ff9788d75627e8e8a9c198c49821ad9826c10e456c-original",
               "banner":"https://d12jj0pnkw1mbj.cloudfront.net/4bdaaff74ee8011fe50609ff9788d75627e8e8a9c198c49821ad9826c10e456c-original",
               "tileUri":"https://d12jj0pnkw1mbj.cloudfront.net/4bdaaff74ee8011fe50609ff9788d75627e8e8a9c198c49821ad9826c10e456c-original",
               "thumbnail":""
            },
            "deployStatus":"DEPLOYED",
            "nftType":"ERC1155",
            "times":{
               "createdAt":1679884580731,
               "updatedAt":1679884580731
            },
            "extra":{
               "properties":{
                  "isLegacy":false,
                  "isPublic":false,
                  "isCounterFactualNFT":true,
                  "isMintable":true,
                  "isEditable":true,
                  "isDeletable":false
               },
               "mintChannel":"UNKNOWN_CHANNEL"
            }
         },
         "updatedAt":1679989655936
      },
      {
         "id":5,
         "accountId":10032,
         "tokenId":32768,
         "nftData":"0x2bd63e2e6ecf3f97f10321a0492bea56bda675e9d5eed42120282a7ed7ee9cae",
         "tokenAddress":"0x4727365e03b1284bdcf62eff5c24ba3cfdb13fe1",
         "nftId":"0x241b290513b0966c330d271fc20862585ce905b194cbd4446ec785f4f970cbba",
         "nftType":"ERC1155",
         "total":"80000",
         "locked":"0",
         "pending":{
            "withdraw":"0",
            "deposit":"0"
         },
         "deploymentStatus":"DEPLOYED",
         "isCounterFactualNFT":true,
         "metadata":{
            "uri":"ipfs://QmQmbQaRrvRDMW8TMyZDHHuH6CxH3aiEsHAgA66kRXQ9Sy",
            "base":{
               "name":"第一个NFT",
               "decimals":-1,
               "description":"这是第一个NFT\n如题",
               "image":"ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
               "properties":"{\"爱上\":\"就是；封控楼\",\"电风扇分散\":\"看了看\"}",
               "localization":"",
               "createdAt":1679884804679,
               "updatedAt":1679989420005
            },
            "imageSize":{
               "240-240":"https://d12jj0pnkw1mbj.cloudfront.net/c33638044379e5f60c3c6eae9563caeff1088bffd3645c28abcf2e996ae08c0c1679989419694-240-240.png",
               "332-332":"https://d12jj0pnkw1mbj.cloudfront.net/c33638044379e5f60c3c6eae9563caeff1088bffd3645c28abcf2e996ae08c0c1679989419694-332-332.png",
               "original":"https://d12jj0pnkw1mbj.cloudfront.net/c33638044379e5f60c3c6eae9563caeff1088bffd3645c28abcf2e996ae08c0c1679989419694-original"
            },
            "extra":{
               "imageData":"",
               "externalUrl":"",
               "attributes":"[{\"trait_type\":\"爱上\",\"value\":\"就是；封控楼\"},{\"trait_type\":\"电风扇分散\",\"value\":\"看了看\"}]",
               "backgroundColor":"",
               "animationUrl":"ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
               "youtubeUrl":"",
               "minter":""
            },
            "status":1,
            "nftType":1,
            "network":0,
            "tokenAddress":"0x4727365e03b1284bdcf62eff5c24ba3cfdb13fe1",
            "nftId":"0x16331250528220135569317024633130487488220842791084189368475259585150288186298"
         },
         "minter":"0xb4a0c11e4d0d434bb4e9a133e5a6b7b058530e22",
         "royaltyPercentage":10,
         "preference":{
            "favourite":false,
            "hide":false
         },
         "collectionInfo":{
            "id":6,
            "owner":"0xb4a0c11e4d0d434bb4e9a133e5a6b7b058530e22",
            "name":"这是第二个collection",
            "contractAddress":"0x4727365e03b1284bdcf62eff5c24ba3cfdb13fe1",
            "collectionAddress":"0x4727365e03b1284bdcf62eff5c24ba3cfdb13fe1",
            "baseUri":"ipfs://0x0953cd56b04dc347ac8ce67a84c17c90cad33a1e79835456965916499c6fba00",
            "nftFactory":"0x0ad87482a1bfd0B3036Bb4b13708C88ACAe1b8bA",
            "description":"随便上传",
            "avatar":"ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
            "banner":"ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
            "thumbnail":"",
            "tileUri":"ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg",
            "cached":{
               "avatar":"https://d12jj0pnkw1mbj.cloudfront.net/4bdaaff74ee8011fe50609ff9788d75627e8e8a9c198c49821ad9826c10e456c-original",
               "banner":"https://d12jj0pnkw1mbj.cloudfront.net/4bdaaff74ee8011fe50609ff9788d75627e8e8a9c198c49821ad9826c10e456c-original",
               "tileUri":"https://d12jj0pnkw1mbj.cloudfront.net/4bdaaff74ee8011fe50609ff9788d75627e8e8a9c198c49821ad9826c10e456c-original",
               "thumbnail":""
            },
            "deployStatus":"DEPLOYED",
            "nftType":"ERC1155",
            "times":{
               "createdAt":1679884580731,
               "updatedAt":1679884580731
            },
            "extra":{
               "properties":{
                  "isLegacy":false,
                  "isPublic":false,
                  "isCounterFactualNFT":true,
                  "isMintable":true,
                  "isEditable":true,
                  "isDeletable":false
               },
               "mintChannel":"UNKNOWN_CHANNEL"
            }
         },
         "updatedAt":1679885013117
      }
   ]
}
```
