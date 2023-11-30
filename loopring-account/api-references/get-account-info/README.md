# Get Account info

## EndPoint

```
GET /api/v3/account
```

## Request

one of owner and accountId is required.

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>owner</td><td>Ethereum address, either owner or accountId should be presented.</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr><tr><td>accountId</td><td>AccountID, if owner is presented, it must be aligned with the owners accountId, otherwise an error occurs.</td><td>10003</td><td>integer</td><td>N</td></tr></tbody></table>

## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>Account ID</td><td>10</td><td>integer</td><td>Y</td></tr><tr><td>owner</td><td>Ethereum address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>frozen</td><td>The frozen state of the account, true stands for frozen, if the account is frozen, the user cannot submit an order.</td><td>false</td><td>boolean</td><td>Y</td></tr><tr><td>publicKey</td><td><a href="./#publickey">PublicKey</a>, The user's public key</td><td>"{x:0x241707b<br>cc6d7a4ccf10<br>304be248d343<br>a527e85f61b4<br>5d721544d027<br>cc1f2fb5f,y:<br>0x302f3a521d<br>bdd1d0eb1944<br>c8323d4ac3b3<br>e9c9201f4aa4<br>3a2565054886<br>369d9c}"</td><td><a href="https://docs.loopring.io/en/dex_apis/getAccount.html#PublicKey">Public<br>Key</a></td><td>Y</td></tr><tr><td>tags</td><td>Comma separated list of tags such as VIP levels, etc</td><td>"vip_1"</td><td>string</td><td>N</td></tr><tr><td>nonce</td><td>nonce</td><td>0</td><td>integer</td><td>Y</td></tr><tr><td>keyNonce</td><td>Nonce of users key change request, for backward compatible</td><td>0</td><td>integer</td><td>Y</td></tr><tr><td>keySeed</td><td>KeySeed of users L2 eddsaKey, the L2 key should be generated from this seed, i.e., L2_EDDSA_KEY=eth.sign(keySeed). Otherwise, users may receive an error when logging into the Loopring DEX</td><td>"Sign this message to access Loopring Exchange: 0xbbbbca6a901c926f240b89eacb641d8aec7aeafd with key nonce: 103"</td><td>string</td><td>Y</td></tr></tbody></table>

##

## Model

### **PublicKey**

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>x</td><td>The public keys x part.</td><td>"0x241707bcc6<br>d7a4ccf10304<br>be248d343a52<br>7e85f61b45d7<br>21544d027cc1<br>f2fb5f"</td><td>string</td><td>Y</td></tr><tr><td>y</td><td>The public keys y part.</td><td>"0x302f3a521d<br>bdd1d0eb1944<br>c8323d4ac3b3<br>e9c9201f4aa4<br>3a2565054886<br>369d9c"</td><td>string</td><td>Y</td></tr></tbody></table>
