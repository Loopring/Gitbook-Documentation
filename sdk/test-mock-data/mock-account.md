# Mock Account

{% code overflow="wrap" lineNumbers="true" %}
```ts
export const LOOPRING_EXPORTED_ACCOUNT = {
  address: "0x727e0fa09389156fc803eaf9c7017338efd76e7f",
  privateKey:
    "491aecdb1d5f6400a6b62fd12a41a86715bbab675c37a4060ba115fecf94083c",
  accountId: 12454,
  address2: "0xb6d8c39D5528357dBCe6BEd82aC71c74e9D19079",
  privateKey2:
    "e020ed769032ba95d9a5207687a663d6198fe2f5cedf28a250f7cbd8c81a5263",
  accountId2: 10488,
  addressCF: "0x23dE4Da688c94a66E8bbE9BCc95CB03b4e209C15",
  accountIdCF: 11632,
  addressContractWallet: "0xD4BD7c71B6d4A09217ccc713f740d6ed8f4EA0cd",
  depositAddress: "0xb684B265f650a77afd27Ce0D95252a7329B5bD72",
  exchangeAddress: "0x2e76EBd1c7c0C8e7c2B875b6d505a260C525d25e",
  whitelistedAddress: "0x35405E1349658BcA12810d0f879Bf6c5d89B512C",
  whitelistedEddkey:
    "0x27a5b716c7309a30703ede3f1a218cdec857e424a31543f8a658e7d2208db33",
  // const eddkeyWhitelisted =
  //   "0x27a5b716c7309a30703ede3f1a218cdec857e424a31543f8a658e7d2208db33";
  //   apiKey: "2PYgTOZwXHkPXtJMlOMG06ZX1QKJInpoky6iYIbtMgmkbfdL4PvxyEOj0LPOfgYX",
  chainId: 5,
  nftTokenAddress: "0x8394cB7e768070217592572582228f62CdDE4FCE",
  nftTokenId: 32768,
  nftId: "0xa0ce8990402955e559799af24ea765b14ffecc32dfa1cce2dadaf20016b074e6",
  nftData: "0x1a2001aac7a1fd00cef07889cdb67b1355f86e5bc9df71cfa44fa1c7b49f598f",
  testNotOx: "727e0fa09389156fc803eaf9c7017338efd76e7f",
  tradeLRCValue: 1000000000000000000,
  tradeETHValue: 0.0001, //same as UI
  gasPrice: 20, // for test
  gasLimit: 200000, // for test
  validUntil: Math.round(Date.now() / 1000) + 30 * 86400,
};
export const CUSTOMER_KEY_SEED = "XXXXXX" + " with key nonce: " + "${nonce}";
```
{% endcode %}
