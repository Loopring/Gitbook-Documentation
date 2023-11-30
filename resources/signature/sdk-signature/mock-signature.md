# Mock Signature

### generateKeyPair

```ts
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
const result = await signatureKeyPairMock(accInfo);
console.log(result.sk);
```



### getEcDSASig: eth\_signTypedData\_v4

```ts
// test case is not allow brock by Mock provider
const result = await sdk.getEcDSASig(
  web3,
  testTypedData,
  LOOPRING_EXPORTED_ACCOUNT.address,
  sdk.GetEcDSASigType.HasDataStruct,
  sdk.ChainId.GOERLI,
  LOOPRING_EXPORTED_ACCOUNT.accountId,
  "",
  sdk.ConnectorNames.Unknown
);
console.log("getEcDSASig:eth_signTypedData_v4",
  result,
  "ecdsaSig+sdk.SigSuffix.Suffix02",
  result.ecdsaSig + sdk.SigSuffix.Suffix02
);
```



### getEcDSASig: personalSign(WithoutDataStruct--Hardware wallet)

```ts
const result = await sdk.getEcDSASig(
  web3,
  testTypedData,
  LOOPRING_EXPORTED_ACCOUNT.address,
  sdk.GetEcDSASigType.WithoutDataStruct,
  sdk.ChainId.GOERLI,
  LOOPRING_EXPORTED_ACCOUNT.accountId,
  "",
  sdk.ConnectorNames.Unknown
);
console.log(
  "getEcDSASig:WithoutDataStruct(personalSign)",
  result,
  "ecdsaSig+sdk.SigSuffix.Suffix03",
  result.ecdsaSig + sdk.SigSuffix.Suffix03
);
```



### getEcDSASig: personalSign(Contract)

```ts
// test case is not allow brock by Mock provider
const result = await sdk.getEcDSASig(
  web3,
  testTypedData,
  LOOPRING_EXPORTED_ACCOUNT.address,
  sdk.GetEcDSASigType.Contract,
  sdk.ChainId.GOERLI,
  LOOPRING_EXPORTED_ACCOUNT.accountId,
  "",
  sdk.ConnectorNames.Unknown
);
console.log(
  "getEcDSASig:personalSign(Contract)",
  result
);
```
