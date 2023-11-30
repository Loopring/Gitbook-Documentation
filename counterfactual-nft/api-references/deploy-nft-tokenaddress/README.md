---
description: Use L2 token to pay and deploy the NFT tokenAddress in Layer 1
---

# Deploy NFT TokenAddress

## EndPoint

```
POST api/v3/nft/deployTokenAddress
```

## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr><tr><td>X-API-SIG</td><td><a href="../../../resources/signature/eddsa-signature/">EDDSA Signature</a>, ,<br><a href="../../../resources/request-signing/">sign the request</a></td><td>"0xccf0a141fce2dc5cbbd4f802c52220e9e2ce260e86704d6258603eb346eefe2d4a450005c362b223b2840d087f7065ea5eee0314531adf6a580fce64c25dca81c"</td><td></td><td>Y</td></tr></tbody></table>

## Request

<table><thead><tr><th width="251.00000000000003">Query Param</th><th>Description</th><th>Example</th><th data-hidden></th><th data-hidden></th><th data-hidden></th></tr></thead><tbody><tr><td>tokenAddress</td><td>nft token address</td><td></td><td></td><td></td><td></td></tr><tr><td>nftData</td><td>nft data</td><td></td><td></td><td></td><td></td></tr><tr><td>transfer</td><td><a href="../../../erc20-tokens/api-references/transfer/">transfer erc20 token</a> structure,<br>transfer <a href="../../../resources/fees/get-nft-offchain-fee/">deploy fee</a>(request type is 13)<br>to <a href="../get-availablebroker/">relayer broker</a></td><td></td><td></td><td></td><td></td></tr></tbody></table>

## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>hash</td><td>Ethereum hash</td><td>"0xfbe124c734308a7cde02849c41b5d3317d36d0af336dc1a88ed4fb6b2802a161"</td><td>string</td><td>Y</td></tr><tr><td>status</td><td>Whether the order was successfully submitted or not, please note, user may query after a while to get real process status, as most offchain requests are async processed<br>Allowable : ['received', 'processing', 'processed', 'failed']</td><td>"received"</td><td>string</td><td>Y</td></tr><tr><td>isIdempotent</td><td>Idempotent of submit transfer response, submit same transfer again idempotent will be true</td><td>"false"</td><td>boolean</td><td>Y</td></tr></tbody></table>
