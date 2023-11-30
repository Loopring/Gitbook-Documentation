# Sample code

### **Request**

```bash
curl 'https://uat2.loopring.io/api/v3/nft/collection/edit' \
  -H 'X-API-KEY: DuuMSExGhJmfqWlxyRQMDVkARW1V9RmvrZEoyl8JZ0DkZ08up291ckGNuLigvVox' \
  -H 'X-API-SIG: 0x0ed0dd0be9642a61dc2fa9657da6c6d34c1c55a74a5e8a3e462bcfcdd50eb79f2caf2e42c93bcad48d845636a162dee263588605b1e51236a920d82c3e47184305b682f62d64ab9c30f750d91b9d73fa6c128a0fede7a335894ffc58cd4e9288' \
  --data-raw '{"accountId":17608,"avatar":"ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg","banner":"ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg","collectionId":261,"description":"afweafawfwe new desc","name":"new name 123","thumbnail":"","tileUri":"ipfs://QmUr8pyxY94wvRTfvKAMF9V8ZL2K1dxT6PiShH349BrPBg"}' \
  --compressed

```

### **Response**

```json
{ "result": true }
```
