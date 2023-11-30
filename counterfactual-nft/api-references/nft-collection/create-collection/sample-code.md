# Sample code

### **Request**

```bash
curl --location --request POST 'https://uat2.loopring.io/api/v3/nft/collection' \
--header 'X-API-KEY: jcTxEZlFrVNkFE9osrr43iC2Qs3FYN34a4gbEPP4IJDj4qiuapd3d4VSMWwtfReo' \
--header 'X-API-SIG: 0x2ed33a593dd8f4676782757f218dbb352e76b425b069deeae5b5afaf89d7dec0090d77da4e548ae46ecf97deb0a2f44f600129d22a9f3817fbeb016446025e6101ec4d2bf04cdcc1a436c8fadf7e809d2d23555b50c6fee6691ab3df62265d7b' \
--header 'Content-Type: application/json' \
--data-raw '{
    "name":"test",
    "owner":"0x1cACC96e5F01e2849E6036F25531A9A064D2FB5f",
    "nftFactory":"0x25315F9878BA07221db684b7ad3676502E914894",
    "tileUri":"ipfs://QmfS4WckWPzn2eNU53zuTM9qYyjUpwWYLKdAywTRenzELq"
}'

```

### **Response**

```json
{
  "contractAddress": "0xebf9abe801995b6714a4ddbe5ebd06405d7fd9a2"
}
```

### **Failed Response**

```json
{
  "resultInfo": {
    "code": 102127,
    "message": "can not use this name, already existed"
  }
}
```

