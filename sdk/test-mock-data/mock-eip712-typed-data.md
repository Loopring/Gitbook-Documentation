# Mock EIP712 Typed Data

{% code lineNumbers="true" %}
```ts
export const testTypedData: EIP712TypedData = {
  types: {
    EIP712Domain: [
      { name: "name", type: "string" },
      { name: "version", type: "string" },
      { name: "chainId", type: "uint256" },
      { name: "verifyingContract", type: "address" },
    ],
    TestTypedData: [
      { name: "from", type: "address" },
      { name: "to", type: "address" },
      { name: "tokenID", type: "uint16" },
    ],
  },
  primaryType: "TestTypedData",
  domain: {
    name: "Loopring Protocol",
    version: "3.6.0",
    chainId: sdk.ChainId.GOERLI,
    verifyingContract: LOOPRING_EXPORTED_ACCOUNT.exchangeAddress,
  },
  message: {
    from: LOOPRING_EXPORTED_ACCOUNT.address,
    to: LOOPRING_EXPORTED_ACCOUNT.address2,
    tokenID: TOKEN_INFO.tokenMap.LRC.tokenId,
  },
};
```
{% endcode %}
