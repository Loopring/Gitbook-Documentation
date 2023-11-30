---
description: Open an account via the Loopring DEX.
---

# Setup a Loopring Account&#x20;

{% hint style="danger" %}
Please update SDK after v3.1.5 and  use UnlockAccount with \``` account.publicKey or `generateKeyPair` with `account.publicKey` ``
{% endhint %}

<details>

<summary>Step 1: Register a wallet address in the Loopring DEX to get an account ID</summary>

There are two ways to register an account on the Loopring DEX to get an account ID:

1. via API - Make a deposit to your address by calling the [Loopring exchange address](../../resources/common-info/get-exchange-info/). Once the Loopring exchange receives your deposit (8 confirmations), it will generate an account id  for your address.
2. via [Website App](https://loopring.io) - Use an account in Loopring Layer 2 to transfer some tokens to your address, after the transfer is successful, this will generate an account id for the payee address.

</details>

<details>

<summary>Step 2: Retrieve account info using  <a href="../api-references/get-account-info/">GET Account info</a> by address</summary>

Using the newly acquired account id, retrieve the account information using the `getAccount` call.

{% code lineNumbers="true" %}
```ts
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
```
{% endcode %}

</details>

<details>

<summary>Step 3: Use <code>keySeed</code> or <code>CUSTOMER_KEY_SEED generateKeyPair</code></summary>

Generate an EdDSA key-pair using ecdsa to sign message. An EdDSA key-pair is needed for making changes to an account in the SDK. You can create a key-seed phrase using the default recommendation or a custom value.

*   #### Default `keySeed`

    \
    Default `keySeed` string format we use looks like the following:&#x20;

```
Sign this message to access Loopring Exchange: %s with key nonce: %d'.
```

You will need to replace `%s` with the [Loopring exchange address](../../resources/common-info/get-exchange-info/), and replace `%d` with the value of the nonce received in the account information from [step 2](setup-a-loopring-account.md#step-2-retrieve-account-info-using-get-account-info-by-address).

{% code overflow="wrap" lineNumbers="true" %}
```typescript
const keySeed = sdk.BaseAPI.KEY_MESSAGE.replace(
      "${exchangeAddress}",
      LOOPRING_EXPORTED_ACCOUNT.exchangeAddress
    ).replace("${nonce}", accInfo.nonce.toString());
const eddsaKey = await sdk.generateKeyPair({
  web3,
  address: accInfo.owner,
  keySeed,
  walletType: sdk.ConnectorNames.MetaMask,
  chainId: sdk.ChainId.GOERLI,
});
console.log("eddsakey:", eddsaKey.sk);
```
{% endcode %}

*   #### Custom keySeed



    Custom keySeed string must end with `with key nonce: ${nonce}`\
    Example:

```
Sign this message to access ${customString} with key nonce: %d
```

You can define the `customString` yourself, `%d` is the nonce received in the account information from [step 2](setup-a-loopring-account.md#step-2-retrieve-account-info-using-get-account-info-by-address).

{% code overflow="wrap" lineNumbers="true" %}
```typescript
// CUSTOMER_KEY_SEED = "XXXXXX" + " with key nonce: " + "${nonce}";
const keySeed = CUSTOMER_KEY_SEED.replace(
  "${nonce}",
  accInfo.nonce.toString()
const eddsaKey = await sdk.generateKeyPair({
  web3,
  address: accInfo.owner,
  keySeed,
  walletType: sdk.ConnectorNames.MetaMask,
  chainId: sdk.ChainId.GOERLI,
});
console.log("eddsakey:", eddsaKey.sk);
```
{% endcode %}

</details>

<details>

<summary>Step 4: Retrieve fees from the exchange <a href="../../resources/fees/get-erc20-offchain-fee/">get fee</a></summary>

In order to update your account, you'll need to retrieve the list of available fees from the exchange.

Get `updateAccount` fee

{% code overflow="wrap" lineNumbers="true" %}
```typescript
const fee = await LoopringAPI.globalAPI.getActiveFeeInfo({
  accountId: accInfo.accountId,
});
console.log("fee:", fee);
```
{% endcode %}

</details>

<details>

<summary>Step 5: <a href="../api-references/update-eddsakey/"><code>updateAccount</code></a> (activate or reset）</summary>

{% code overflow="wrap" lineNumbers="true" %}
```typescript
 const result = await LoopringAPI.userAPI.updateAccount({
  request: {
    exchange: LOOPRING_EXPORTED_ACCOUNT.exchangeAddress,
    owner: accInfo.owner,
    accountId: accInfo.accountId,
    publicKey: {x: eddsaKey.formatedPx, y: eddsaKey.formatedPy},
    maxFee: {
      tokenId: TOKEN_INFO.tokenMap["LRC"].tokenId,
      volume: fee.fees["LRC"].fee ?? "9400000000000000000",
    },
    keySeed,
    validUntil: LOOPRING_EXPORTED_ACCOUNT.validUntil,
    nonce: accInfo.nonce as number,
  },
  web3,
  chainId: sdk.ChainId.GOERLI,
  walletType: sdk.ConnectorNames.Unknown,
  isHWAddr: false,
});

const {accInfo: updateAccountInfo} =
  await LoopringAPI.exchangeAPI.getAccount({
    owner: LOOPRING_EXPORTED_ACCOUNT.address,
  });
console.log(
  "updateAccount Result: ",
  result,
  "updateAccountInfo:",
  updateAccountInfo
);
```
{% endcode %}

</details>

<details>

<summary>Step 6: <a href="../api-references/get-account-info/">Get account</a> to check update complete</summary>

Check that the `publicKey` is the same as the value set in the previous step and frozen is false.

'frozen' will be true until `updateAccount` completes and then it will be set to false.

You can call this API every 10s until `updateAccount` is complete.

{% code overflow="wrap" lineNumbers="true" %}
```typescript
const {accInfo} = await LoopringAPI.exchangeAPI.getAccount({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
});
```
{% endcode %}

</details>

<details>

<summary>Step 7: Retrieve account API key <a href="../api-references/get-apikey/">Get apiKey</a></summary>

Get the `apiKey` by eddsa signature and then the `apiKey` can be used to get user assets or to call other APIs

{% code overflow="wrap" lineNumbers="true" %}
```typescript
const apiKey = (
      await LoopringAPI.userAPI.getUserApiKey(
        {
          accountId: accInfo.accountId,
        },
        eddsaKey.sk
      )
    ).apiKey;
```
{% endcode %}

</details>
