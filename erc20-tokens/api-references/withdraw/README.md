---
description: Withdraw ERC20 tokens from your layer2 to address in layer1
---

# Withdraw

## EndPoint

```
POST /api/v3/user/withdrawals 
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr><tr><td>X-API-SIG</td><td><a href="../../../resources/signature/ecdsa-signature/">ECDSA Signature</a>, pay attention the signature type,<br>sign the <a href="./#compute-ecdsa-hash">ecdsa hash</a></td><td>"0xccf0a141fce2dc5cbbd4f802c52220e9e2ce260e86704d6258603eb346eefe2d<br>4a450005c362b223b28402d087f7065ea5eee0314531adf6a580fce64c25dca81c02"</td><td></td><td>Y</td></tr></tbody></table>



## Request

<table><thead><tr><th width="150">Query Param</th><th>Description</th><th>Example</th><th data-hidden></th><th data-hidden></th><th data-hidden></th></tr></thead><tbody><tr><td>exchange</td><td>exchangeAddress in <a href="../../../resources/common-info/get-exchange-info/">exchange info</a></td><td></td><td></td><td></td><td></td></tr><tr><td>owner</td><td>account owner address</td><td></td><td></td><td></td><td></td></tr><tr><td>accountId</td><td>account ID</td><td>10110</td><td></td><td></td><td></td></tr><tr><td>token</td><td><a href="./#tokenvolume">tokenVolume</a>，withdraw tokenId and volume</td><td></td><td></td><td></td><td></td></tr><tr><td>to</td><td>withdraw to address</td><td></td><td></td><td></td><td></td></tr><tr><td>maxFee</td><td><a href="./#tokenvolume">tokenVolume</a> from <a href="../../../resources/fees/get-erc20-offchain-fee/">offchain fee</a></td><td></td><td></td><td></td><td></td></tr><tr><td>storageId</td><td>offchainId of <a href="../../../resources/storage-id/">storage Id</a></td><td>1</td><td></td><td></td><td></td></tr><tr><td>validUntil</td><td>Timestamp for withdraw to become invalid, seconds</td><td><p></p><p>normally current time + 2 months</p></td><td></td><td></td><td></td></tr><tr><td>eddsaSignature</td><td><a href="../../../resources/signature/eddsa-signature/">eddsa signature</a><br>of the <a href="./#compute-eddsa-hash">eddsa hash</a></td><td></td><td></td><td></td><td></td></tr><tr><td>minGas</td><td>withdraw gas, set to 0 now</td><td>0</td><td></td><td></td><td></td></tr><tr><td>extraData</td><td>set to "" now</td><td>""</td><td></td><td></td><td></td></tr><tr><td>payPayeeUpdateAccount</td><td><a href="../../../resources/advanced/pay-payee-updateaccount-fee.md">(Optional) transfer to pay payee updateAccount fee</a></td><td>true</td><td></td><td></td><td></td></tr><tr><td>counterFactualInfo</td><td><a href="./#undefined-1">(Optional) counterFactual Wallet Info</a></td><td>if it's counterFactual wallet, need pass the info</td><td></td><td></td><td></td></tr></tbody></table>



## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>hash</td><td>The hash identifier set by the user at the time of submission, can use this hash to get the withdrawal info</td><td>"0x1d923ca783<br>4dc90484fa2e<br>b611f0f0bc7e<br>741bb107007e<br>bea19ba8caea<br>b4f9d3"</td><td>string</td><td>Y</td></tr><tr><td>status</td><td>Whether the order was successfully submitted or not, please note, the user may query after a while to get the real process status, as most off-chain requests are async processed<br>Allowable : ['received', 'processing', 'processed', 'failed']</td><td>"received"</td><td>string</td><td>Y</td></tr><tr><td>isIdempotent</td><td>Idempotent of submit transfer response, submit same transfer again idempotent will be true</td><td>"false"</td><td>boolean</td><td>Y</td></tr></tbody></table>



## Model

### TokenVolume

Wrapper object used to describe a token associated with a certain quantity.

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>tokenId</td><td>The Loopring's token identifier.</td><td>0</td><td>integer</td><td>Y</td></tr><tr><td>volume</td><td>The volume of the token</td><td>"100000000000<br>0"</td><td>string</td><td>Y</td></tr></tbody></table>



### counterFactualInfo

counterFactual Wallet Info

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>walletFactory</td><td>Counterfactual wallet factory contract address</td><td>"0xbbbbca6a90<br>1c926f240b89<br>eacb641d8aec<br>7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>walletOwner</td><td>Counterfactual wallet owner address, NOT the wallet address</td><td>"0xbbbbca6a90<br>1c926f240b89<br>eacb641d8aec<br>7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>walletSalt</td><td>Salt to generate address from owner &#x26; other related info</td><td>"1"</td><td>string</td><td>Y</td></tr></tbody></table>



## Compute ECDSA hash

```
const typedData: EIP712TypedData = {
    types: {
      EIP712Domain: [
        { name: "name", type: "string" },
        { name: "version", type: "string" },
        { name: "chainId", type: "uint256" },
        { name: "verifyingContract", type: "address" },
      ],
      Withdrawal: [
        { name: "owner", type: "address" },
        { name: "accountID", type: "uint32" },
        { name: "tokenID", type: "uint16" },
        { name: "amount", type: "uint96" },
        { name: "feeTokenID", type: "uint16" },
        { name: "maxFee", type: "uint96" },
        { name: "to", type: "address" },
        { name: "extraData", type: "bytes" },
        { name: "minGas", type: "uint256" },
        { name: "validUntil", type: "uint32" },
        { name: "storageID", type: "uint32" },
      ],
    },
    primaryType: "Withdrawal",
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

const onchainDataHash = abi
    .soliditySHA3(
      ["uint256", "address", "bytes"],
      [
        request.minGas,
        new BN(fm.clearHexPrefix(request.to), 16),
        ethUtil.toBuffer(request.extraData),
      ]
    )
    .slice(0, 20);

const orderHashStr = fm.addHexPrefix(onchainDataHash.toString("hex"));
const inputs = [
    new BN(ethUtil.toBuffer(request.exchange)).toString(),
    request.accountId,
    request.token.tokenId,
    request.token.volume,
    request.maxFee.tokenId,
    request.maxFee.volume,
    orderHashStr,
    request.validUntil,
    request.storageId,
  ];
const hasher = Poseidon.createHash(inputs.length + 1, 6, 53);
const hash = hasher(inputs).toString(10);
```
