---
description: withdraw nft to layer1
---

# Withdraw NFT

## EndPoint

```
POST api/v3/nft/withdrawal
```

## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr><tr><td>X-API-SIG</td><td><a href="../../../resources/signature/ecdsa-signature/">ECDSA Signature</a>, pay attention the signature type,<br>sign the <a href="./#compute-ecdsa-hash">ecdsa hash</a></td><td>"0xccf0a141fce2dc5cbbd4f802c52220e9e2ce260e86704d6258603eb346eefe2d<br>4a450005c362b223b2842d087f7065ea5eee0314531adf6a580fce64c25dca81c02"</td><td></td><td>Y</td></tr></tbody></table>

## Request

<table><thead><tr><th width="247.00000000000003">Query Param</th><th width="253">Description</th><th>Example</th><th data-hidden></th><th data-hidden></th><th data-hidden></th></tr></thead><tbody><tr><td>exchange</td><td>exchangeAddress in <a href="../../../resources/common-info/get-exchange-info/">exchange info</a></td><td></td><td></td><td></td><td></td></tr><tr><td>owner</td><td>account owner address</td><td></td><td></td><td></td><td></td></tr><tr><td>accountId</td><td>sender accountId</td><td>10110</td><td></td><td></td><td></td></tr><tr><td>to</td><td>withdraw to address</td><td></td><td></td><td></td><td></td></tr><tr><td>token</td><td><a href="./#nfttokenamountinfo">NftTAmountInfo</a>, withdraw nft info</td><td></td><td></td><td></td><td></td></tr><tr><td>maxFee</td><td><p><a href="./#tokenamountinfo">TokenAmountInfo</a>,</p><p><a href="../../../resources/fees/get-nft-offchain-fee/">offchain fee,</a> request type is 10.<br>Note: if the tokenAddress isn't deployed yet, the fee is <code>deploy fee + withdraw fee</code>, and the tokenAddress will be deployed in withdraw.</p></td><td></td><td></td><td></td><td></td></tr><tr><td>storageId</td><td>offchainId of <a href="../../../resources/storage-id/">storage Id</a>, sellTokenId is nft tokenId in nft balance</td><td>1</td><td></td><td></td><td></td></tr><tr><td>validUntil</td><td>Timestamp for transfer to become invalid, seconds</td><td><p></p><p>normally current time + 2 months</p></td><td></td><td></td><td></td></tr><tr><td>eddsaSignature</td><td><a href="../../../resources/signature/eddsa-signature/">eddsa signature</a><br>of the <a href="./#compute-eddsa-hash">eddsa hash</a></td><td></td><td></td><td></td><td></td></tr><tr><td>counterFactualInfo</td><td><a href="./#counterfactualinfo">(Optional) counterFactual Wallet Info</a></td><td>if it's a counterFactual wallet, need to pass the info</td><td></td><td></td><td></td></tr><tr><td>minGas</td><td><mark style="color:orange;">(Optional)</mark> min gas for on-chain withdraw, Loopring exchange allocates gas for each distribution, but people can also assign this min gas, so Loopring have to allocate higher gas value for this specific distribution, 0 means let Loopring choose the reasonable gas</td><td>0</td><td></td><td></td><td></td></tr></tbody></table>

## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>hash</td><td>The hash identifier set by the user at the time of submission, can use this hash to get the transfer info</td><td>"0x1d923ca7834dc90484fa2eb611f0f0bc7e741bb107007ebea19ba8caeab4f9d3"</td><td>string</td><td>Y</td></tr><tr><td>status</td><td>Whether the order was successfully submitted or not, please note, user may query after a while to get real process status, as most offchain requests are async processed<br>Allowable : ['received', 'processing', 'processed', 'failed']</td><td>"received"</td><td>string</td><td>Y</td></tr><tr><td>isIdempotent</td><td>Idempotent of submit transfer response, submit same transfer again idempotent will be true</td><td>"false"</td><td>boolean</td><td>Y</td></tr></tbody></table>

##

## Model

### **NftTokenAmountInfo**

Wrapper object used to describe a token associated with a certain quantity.

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>tokenId</td><td>The Loopring's NFT token identifier.</td><td>32769</td><td>integer</td><td>Y</td></tr><tr><td>amount</td><td><p>The amount of the NFT</p><p> token</p></td><td>"2"</td><td>string</td><td>Y</td></tr><tr><td>nftData</td><td>The Loopring's NFT token data identifier which is a hash string of NFT token address and NFT_ID</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa 8ca7100400f7c31085"</td><td></td><td></td></tr></tbody></table>

### TokenAmountInfo

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>tokenId</td><td>The Loopring's ERC20 token identifier.</td><td>0</td><td>integer</td><td>Y</td></tr><tr><td>amount</td><td>The amount of the ERC20 token</td><td>"100000000000000000"</td><td>string</td><td>Y</td></tr></tbody></table>

\


### counterFactualInfo

counterFactual Wallet Info

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>walletFactory</td><td>Counter factual wallet factory contract address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>walletOwner</td><td>Counter factual wallet owner address, NOT the wallet address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>walletSalt</td><td>Salt to generate address from owner &#x26; other related info</td><td>"1"</td><td>string</td><td>Y</td></tr></tbody></table>

## Compute ECDSA hash

```
const message = {
    owner: data.owner,
    accountID: data.accountId,
    tokenID: data.token.tokenId,
    amount: data.token.amount,
    feeTokenID: data.maxFee.tokenId,
    maxFee: data.maxFee.amount,
    to: data.to,
    extraData: data.extraData ? data.extraData : "",
    minGas: data.minGas,
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
    request.token.amount,
    request.maxFee.tokenId,
    request.maxFee.amount,
    orderHashStr,
    request.validUntil,
    request.storageId,
  ];
  
  const hasher = Poseidon.createHash(inputs.length + 1, 6, 53);
  const hash = hasher(inputs).toString(10);
```
