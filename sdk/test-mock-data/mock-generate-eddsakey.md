# Mock Generate eddsaKey

{% code lineNumbers="true" %}
```ts
export async function signatureKeyPairMock(
  accInfo: sdk.AccountInfo,
  _web3: Web3 = web3
) {
  const eddsaKey = await sdk.generateKeyPair({
    web3: _web3,
    address: accInfo.owner,
    keySeed:
      accInfo.keySeed ??
      sdk.GlobalAPI.KEY_MESSAGE.replace(
        "${exchangeAddress}",
        LOOPRING_EXPORTED_ACCOUNT.exchangeAddress
      ).replace("${nonce}", (accInfo.nonce - 1).toString()),
    walletType: sdk.ConnectorNames.MetaMask,
    chainId: sdk.ChainId.GOERLI,
  });
  return eddsaKey;
}
```
{% endcode %}
