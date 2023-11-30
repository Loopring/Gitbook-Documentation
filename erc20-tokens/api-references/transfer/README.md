---
description: Sending ERC20 tokens from your Loopring L2 to another Loopring L2 address.
---

# Transfer

## EndPoint

```
POST api/v3/transfer
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr><tr><td>X-API-SIG</td><td><a href="../../../resources/signature/ecdsa-signature/">ECDSA Signature</a>, pay attention the signature type,<br>sign the <a href="./#compute-ecdsa-hash">ecdsa hash</a></td><td>"0xccf0a141fce2dc5cbbd4f802c52220e9e2ce260e86704d6258603eb346eefe2d4a450005c362b223b2842d087f7065ea5eee0314531adf6a580fce64c25dca81c02"</td><td></td><td>Y</td></tr></tbody></table>



## Request

<table><thead><tr><th width="150">Query Param</th><th>Description</th><th>Example</th><th data-hidden></th><th data-hidden></th><th data-hidden></th></tr></thead><tbody><tr><td>exchange</td><td>exchangeAddress in <a href="../../../resources/common-info/get-exchange-info/">exchange info</a></td><td></td><td></td><td></td><td></td></tr><tr><td>payerAddr</td><td>payer address</td><td></td><td></td><td></td><td></td></tr><tr><td>payerId</td><td>payer account ID</td><td>10110</td><td></td><td></td><td></td></tr><tr><td>payeeAddr</td><td>payee address</td><td></td><td></td><td></td><td></td></tr><tr><td>payeeId</td><td>payee account ID</td><td>10111，can set to 0 if dont have</td><td></td><td></td><td></td></tr><tr><td>token</td><td><a href="./#tokenvolume">tokenVolume</a>，transfer tokenId and volume</td><td></td><td></td><td></td><td></td></tr><tr><td>maxFee</td><td><a href="./#tokenvolume">tokenVolume</a> from <a href="../../../resources/fees/get-erc20-offchain-fee/">offchain fee</a></td><td></td><td></td><td></td><td></td></tr><tr><td>storageId</td><td>offchainId of <a href="../../../resources/storage-id/">storage Id</a>, sellTokenId is the transfer tokenId</td><td>1</td><td></td><td></td><td></td></tr><tr><td>validUntil</td><td>Timestamp for transfer to become invalid, seconds</td><td><p></p><p>normally current time + 2 months</p></td><td></td><td></td><td></td></tr><tr><td>eddsaSignature</td><td><a href="../../../resources/signature/eddsa-signature/">eddsa signature</a><br>of the <a href="./#undefined">transfer eddsa hash</a></td><td></td><td></td><td></td><td></td></tr><tr><td>memo</td><td><mark style="color:orange;">(Optional)</mark> memo</td><td></td><td></td><td></td><td></td></tr><tr><td>payPayeeUpdateAccount</td><td><a href="../../../resources/advanced/pay-payee-updateaccount-fee.md">(Optional) transfer to pay payee updateAccount fee</a> , true or false, default is false</td><td>true</td><td></td><td></td><td></td></tr><tr><td>counterFactualInfo</td><td><a href="./#undefined-1">(Optional) counterfactual Wallet Info</a>, if it's a counterfactual wallet, need to pass the info</td><td></td><td></td><td></td><td></td></tr></tbody></table>



## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>hash</td><td>The hash identifier set by the user at the time of submission, can use this hash to get the transfer info</td><td>"0x1d923ca7834dc90484fa2eb611f0f0bc7e741bb107007ebea19ba8caeab4f9d3"</td><td>string</td><td>Y</td></tr><tr><td>status</td><td>Whether the order was successfully submitted or not, please note, the user may query after a while to get the real  process status, as most off-chain requests are asynchronously processed<br>Allowable : ['received', 'processing', 'processed', 'failed']</td><td>"received"</td><td>string</td><td>Y</td></tr><tr><td>isIdempotent</td><td>Idempotent of submit transfer response, submit same transfer again idempotent will be true</td><td>"false"</td><td>boolean</td><td>Y</td></tr></tbody></table>



## Model

### TokenVolume

Wrapper object used to describe a token associated with a certain quantity.

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>tokenId</td><td>The Loopring's token identifier.</td><td>0</td><td>integer</td><td>Y</td></tr><tr><td>volume</td><td>The volume of the token</td><td>"100000000000<br>0"</td><td>string</td><td>Y</td></tr></tbody></table>



### counterFactualInfo

Counterfactual wallet information.

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>walletFactory</td><td>Counterfactual wallet factory contract address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>walletOwner</td><td>Counterfactual wallet owner address, NOT the wallet address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>walletSalt</td><td>Salt to generate address from owner &#x26; other related info</td><td>"1"</td><td>string</td><td>Y</td></tr></tbody></table>



## Compute ECDSA hash

```
const message = {
    from: data.payerAddr,
    to: data.payeeAddr,
    tokenID: data.token.tokenId,
    amount: data.token.volume,
    feeTokenID: data.maxFee.tokenId,
    maxFee: data.maxFee.volume,
    validUntil: data.validUntil,
    storageID: data.storageId,
  };
const typedData: EIP712TypedData = {
    types: {
      EIP712Domain: [
        { name: "name", type: "string" },
        { name: "version", type: "string" },
        { name: "chainId", type: "uint256" },
        { name: "verifyingContract", type: "address" },
      ],
      Transfer: [
        { name: "from", type: "address" },
        { name: "to", type: "address" },
        { name: "tokenID", type: "uint16" },
        { name: "amount", type: "uint96" },
        { name: "feeTokenID", type: "uint16" },
        { name: "maxFee", type: "uint96" },
        { name: "validUntil", type: "uint32" },
        { name: "storageID", type: "uint32" },
      ],
    },
    primaryType: "Transfer",
    domain: {
      name: "Loopring Protocol",
      version: "3.6.0",
      chainId: chainId,
      verifyingContract: data.exchange,
    },
    message: message,
  };
```



## Compute EdDSA hash

```
const inputs = [
    new BN(ethUtil.toBuffer(request.exchange)).toString(),
    request.payerId,
    request.payeeId,
    request.token.tokenId,
    request.token.volume,
    request.maxFee.tokenId,
    request.maxFee.volume,
    new BN(ethUtil.toBuffer(request.payeeAddr)).toString(),
    0,
    0,
    request.validUntil,
    request.storageId,
];
const hasher = Poseidon.createHash(inputs.length + 1, 6, 53);
const hash = hasher(inputs).toString(10);
```
