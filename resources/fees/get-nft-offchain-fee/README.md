---
description: get fee of mint, transfer, withdraw. etc
---

# GET NFT Offchain Fee

## EndPoint

```
GET api/v3/user/nft/offchainFee
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td>string</td><td>Y</td></tr></tbody></table>



## Request

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>Account ID</td><td>10110</td><td>integer</td><td>Y</td></tr><tr><td>requestType</td><td>Off-chain request type Allowable : ['9:NFT_MINT', '10:NFT_WITHDRAWAL', '11:NFT_TRANSFER', '13:DEPLOY_TOKENADDRESS', '19:NFT_TRANSFER_AND_UPDATE_ACCOUNT']</td><td>9</td><td>integer</td><td>Y</td></tr><tr><td>tokenAddress</td><td>(Optional) the NFT tokenAddress, needed when requestType is 9 or 10</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr><tr><td>deployInWithdraw</td><td>(Optional) Deploy the counterFactual NFT token when withdraw, if the contract not deployed and you want to deploy it when withdraw, need set to true to get the withdrawal fee</td><td>true</td><td></td><td></td></tr></tbody></table>



## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>gasPrice</td><td>gasPrice when calculating the fee</td><td>2194508101</td><td>string</td><td>Y</td></tr><tr><td>fees</td><td>List[<a href="./#tokenfee">TokenFee</a>]</td><td></td><td>string</td><td>Y</td></tr></tbody></table>



## Model

### TokenFee

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>token</td><td>fee token</td><td>"ETH"</td><td>string</td><td>Y</td></tr><tr><td>fee</td><td>fee amount</td><td>"200000000000<br>0000"</td><td>string</td><td>Y</td></tr><tr><td>discount</td><td>token discount. 0.8 means 80% of the fee</td><td>1.0</td><td>number</td><td>Y</td></tr></tbody></table>
