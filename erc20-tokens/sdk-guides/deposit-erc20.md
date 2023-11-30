---
description: Deposit ERC20 from Ethereum L1 to Loopring L2
---

# Deposit ERC20

This action will require a gas fee for interacting with Ethereum Layer1, please be sure the account used has enough ETH to perform the action. \
\
Be aware there is a slight difference in processes to deposit **ETH** versus **ERC20 tokens**.

{% hint style="info" %}
**All Deposit Methods: Users should have enough `ETH` to pay for the Ethereum Gas fee (Loopring does not charge a fee for Deposit).**

Provider will give the Gas Price & Limit. SDK will also have a method to get the gasPrice: `const gasPrice = (await LoopringAPI.exchangeAPI.getGasPrice() ).gasPrice;`
{% endhint %}

## Depositing ETH

<details>

<summary>Step 1: Get nonce</summary>

{% code lineNumbers="true" %}
```typescript
const nonce = await sdk.getNonce(web3, LOOPRING_EXPORTED_ACCOUNT.address);
console.log(
  `deposit: ${TOKEN_INFO.tokenMap.ETH.symbol}-${LOOPRING_EXPORTED_ACCOUNT.tradeETHValue}, gasPrice: ${LOOPRING_EXPORTED_ACCOUNT.gasPrice}, `
);
```
{% endcode %}

</details>

<details>

<summary>Step 2: Deposit</summary>

<pre class="language-typescript" data-line-numbers><code class="lang-typescript"><strong>const response = await sdk.deposit(
</strong>  web3,
  LOOPRING_EXPORTED_ACCOUNT.address,
  LOOPRING_EXPORTED_ACCOUNT.exchangeAddress,
  TOKEN_INFO.tokenMap.ETH,
  LOOPRING_EXPORTED_ACCOUNT.tradeETHValue,
  0,
  LOOPRING_EXPORTED_ACCOUNT.gasPrice,
  LOOPRING_EXPORTED_ACCOUNT.gasLimit,
  sdk.ChainId.GOERLI,
  nonce,
  true
);

console.log(`nonce: ${nonce} deposit_ETH: `, response);
</code></pre>

</details>

###

## Depositing ERC20 Tokens

<details>

<summary>Step 1: Get allowances</summary>

{% code lineNumbers="true" %}
```typescript
const {tokenAllowances} = await LoopringAPI.exchangeAPI.getAllowances({
  owner: LOOPRING_EXPORTED_ACCOUNT.address,
  token: [TOKEN_INFO.tokenMap.LRC.address],
});
if (
  tokenAllowances.has(TOKEN_INFO.tokenMap.LRC.address) &&
  Number(tokenAllowances.get(TOKEN_INFO.tokenMap.LRC.address)) <
  LOOPRING_EXPORTED_ACCOUNT.tradeLRCValue
) {
  const nonce = await web3.eth.getTransactionCount(
    LOOPRING_EXPORTED_ACCOUNT.address
  );
  await sdk.approveMax(
    web3,
    LOOPRING_EXPORTED_ACCOUNT.address,
    TOKEN_INFO.tokenMap.LRC.address, // LRC address  {tokenIdMap} = getTokens();  tokenIdMap['LRC']
    LOOPRING_EXPORTED_ACCOUNT.depositAddress, //{exchangeInfo} = getExchangeInfo()  exchangeInfo.depositAddress
    LOOPRING_EXPORTED_ACCOUNT.gasPrice,
    LOOPRING_EXPORTED_ACCOUNT.gasLimit,
    sdk.ChainId.GOERLI,
    nonce,
    true
  );
}
```
{% endcode %}

</details>

<details>

<summary>Step 2: Get nonce</summary>

{% code lineNumbers="true" %}
```typescript
tyconst nonce = await sdk.getNonce(web3, LOOPRING_EXPORTED_ACCOUNT.address);
console.log(
  `deposit: ${TOKEN_INFO.tokenMap.LRC.symbol}-${LOOPRING_EXPORTED_ACCOUNT.tradeLRCValue}, gasPrice: ${LOOPRING_EXPORTED_ACCOUNT.gasPrice}, `
);
```
{% endcode %}

</details>

<details>

<summary>Step 3: Deposit</summary>

{% code lineNumbers="true" %}
```typescript
const response = await sdk.deposit(
  web3,
  LOOPRING_EXPORTED_ACCOUNT.address,
  LOOPRING_EXPORTED_ACCOUNT.exchangeAddress,
  TOKEN_INFO.tokenMap.LRC,
  sdk
    .toBig(LOOPRING_EXPORTED_ACCOUNT.tradeLRCValue)
    .div("1e" + TOKEN_INFO.tokenMap.LRC.decimals)
    .toNumber(),
  0,
  LOOPRING_EXPORTED_ACCOUNT.gasPrice,
  LOOPRING_EXPORTED_ACCOUNT.gasLimit,
  sdk.ChainId.GOERLI,
  nonce,
  true
);

console.log(`nonce: ${nonce}  deposit_LRC: `, response);
```
{% endcode %}

</details>
