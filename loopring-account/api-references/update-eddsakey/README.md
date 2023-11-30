# Update EddsaKey

## EndPoint

```
POST /api/v3/account
```

## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-SIG</td><td><a href="../../../resources/signature/ecdsa-signature/">ECDSA Signature</a>, it's the <a href="../../../resources/request-signing/#special-api-request-signatures">request signing</a></td><td>"0xccf0a141fce2dc5cbbd4f802c52220e9e2ce260e86704d6258603eb346eefe2d4a450005c362b223b2842d087f7065ea5eee0314531adf6a580fce64c25dca81c02"</td><td></td><td>Y</td></tr></tbody></table>

## Request

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>exchange</td><td>exchange address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>owner</td><td>owner address</td><td>"0xB4A70168340C75119523019f79F5Ffd9c60DceC7"</td><td>string</td><td>Y</td></tr><tr><td>accountId</td><td>user account ID</td><td>10010</td><td>integer</td><td>Y</td></tr><tr><td>publicKey</td><td><a href="./#publickey">PublicKey</a>, The user's public key</td><td>{x:0x241707bcc6d7a4ccf10304be248d343a527e85f61b45d721544d027cc1f2fb5f,y:0x302f3a521dbdd1d0eb1944c8323d4ac3b3e9c9201f4aa43a2565054886369d9c}</td><td><a href="https://docs.loopring.io/en/dex_apis/submitUpdateAccount.html#PublicKey">Public<br>Key</a></td><td>Y</td></tr><tr><td>maxFee</td><td>TokenAmount, maximum of fee token</td><td>"{tokenId: 0, volume: 1000000}"</td><td><a href="https://docs.loopring.io/en/dex_apis/submitUpdateAccount.html#TokenVolumeV3">Token<br>VolumeV3</a></td><td>Y</td></tr><tr><td>validUntil</td><td>Timestamp for order to become invalid</td><td>1583183141</td><td>integer</td><td>Y</td></tr><tr><td>nonce</td><td>Nonce of users exchange account that used in off-chain requests.</td><td>1</td><td>integer</td><td>Y</td></tr><tr><td>keySeed</td><td>KeySeed of users L2 eddsaKey, the L2 key should be generated from this seed, i.e., L2_EDDSA_KEY=eth.sign(keySeed). Otherwise, user may meet error in login loopring DEX</td><td>"Sign this message to access Loopring Exchange: 0xbbbbca6a901c926f240b89eacb641d8aec7aeafd with key nonce: 103"</td><td>string</td><td>N</td></tr><tr><td>counterFactualInfo</td><td>(Optional) Counterfactual wallet extra info to verify L1 ecdsa signature.</td><td>"{walletFacto<br>ry: 0xABCD, walletOwner: 0xABCD, walletSalt: 1234}"</td><td><a href="https://docs.loopring.io/en/dex_apis/submitUpdateAccount.html#CounterFactualInfo">Counter<br>Factual<br>Info</a></td><td>N</td></tr></tbody></table>

## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>hash</td><td>The order hash identifier set by the user at the time of submission</td><td>"0x1d923ca7834dc90484fa2eb611f0f0bc7e741bb107007ebea19ba8caeab4f9d3"</td><td>string</td><td>Y</td></tr><tr><td>status</td><td>Whether the order was successfully submitted or not, please note, that the user may query after a while to get real process status, as most off-chain requests are async processed<br>Allowable : ['received', 'processing', 'processed', 'failed']</td><td>"processing"</td><td>string</td><td>Y</td></tr><tr><td>isIdempotent</td><td>Idempotent of submit order response, submit same order again when order was UNKNOWN or WAIT_FREEZE_BALANCE in relayer, idempotent will be true<br>Allowable : [True, False]</td><td>false</td><td>boolean</td><td>Y</td></tr></tbody></table>

##

## Model

### **PublicKey**

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>x</td><td>The public keys x part.</td><td>"0x241707bcc6<br>d7a4ccf10304<br>be248d343a52<br>7e85f61b45d7<br>21544d027cc1<br>f2fb5f"</td><td>string</td><td>Y</td></tr><tr><td>y</td><td>The public keys y part.</td><td>"0x302f3a521d<br>bdd1d0eb1944<br>c8323d4ac3b3<br>e9c9201f4aa4<br>3a2565054886<br>369d9c"</td><td>string</td><td>Y</td></tr></tbody></table>

