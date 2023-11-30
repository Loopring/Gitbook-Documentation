---
description: Exist Account Login again
---

# Unlock Account (Login)

{% hint style="danger" %}
Please update SDK after v3.1.5 and  use UnlockAccount with \``` account.publicKey or `generateKeyPair` with `account.publicKey` ``
{% endhint %}

<details>

<summary>Step 1:  <a href="../api-references/get-account-info/">GET Account info</a> by address</summary>

{% code lineNumbers="true" %}
```ts
const account = LoopringAPI.exchangeAPI.getAccount({
  owner: accounStore.accAddress,
})
```
{% endcode %}

</details>

<details>

<summary>Step 2: Nonce &#x26; keySeed</summary>

{% code lineNumbers="true" %}
```ts
const nonce = account ? account.nonce : accounStore.nonce;

const msg =
  account.keySeed && account.keySeed !== ""
    ? account.keySeed
    : sdk.GlobalAPI.KEY_MESSAGE.replace(
      "${exchangeAddress}",
      LOOPRING_EXPORTED_ACCOUNT.exchangeAddress
    ).replace("${nonce}", (nonce - 1).toString());
```
{% endcode %}

</details>

<details>

<summary>Step 3: UnlockAccount</summary>

{% code lineNumbers="true" %}
```ts
const response = await LoopringAPI.userAPI.unLockAccount(
  {
    keyPair: {
      web3: connectProvides.usedWeb3 as unknown as Web3,
      address: account.owner,
      keySeed: msg,
      walletType: connectName,
      chainId: Number(chainId),
      accountId: Number(account.accountId),
      isMobile: isMobile,
    },
    request: {
      accountId: account.accountId,
    },
  },
  account.publicKey
);
```
{% endcode %}

</details>

```
```
