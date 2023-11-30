# Mock provider

{% code lineNumbers="true" %}
```ts
const provider = new PrivateKeyProvider(
LOOPRING_EXPORTED_ACCOUNT.privateKey,
"https://goerli.infura.io/v3/a06ed9c6b5424b61beafff27ecc3abf3"
);
const provider2 = new PrivateKeyProvider(
LOOPRING_EXPORTED_ACCOUNT.privateKey2,
"https://goerli.infura.io/v3/a06ed9c6b5424b61beafff27ecc3abf3"
);
export const web3 = new Web3(provider);
export const web3_2 = new Web3(provider2);
```
{% endcode %}
