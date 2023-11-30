---
description: Get pending txs to be packed into the next block
---

# Get pending transactions



## EndPoint

```
GET api/v3/block/getPendingRequests
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td>string</td><td>Y</td></tr></tbody></table>



## Request

None



## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>txType</td><td>The txType of the transaction, one in [Noop,Deposit,Withdraw,Transfer,SpotTrade,AccountUpdate,AmmUpdate,JoinAmm,ExitAmm,SignatureVerification,NftMint,NftData]<br>Allowable : ['Noop', 'Deposit', 'Withdraw', 'Transfer', 'SpotTrade', 'AccountUpdate', 'AmmUpdate', 'JoinAmm', 'ExitAmm', 'SignatureVerification', 'NftMint', 'NftData']</td><td>"transfer"</td><td>string</td><td>Y</td></tr><tr><td>accountId</td><td>[Optional] The accountId of the transaction</td><td>10006</td><td>integer</td><td>N</td></tr><tr><td>owner</td><td>[Optional] The owner of the transaction</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr><tr><td>token</td><td>[Optional] <a href="get-pending-transactions.md#token">Token</a>, The token info of the transaction</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getPendingRequests.html#_Token">_Token</a></td><td>N</td></tr><tr><td>toToken</td><td>[Optional] <a href="get-pending-transactions.md#token">Token</a>, The toToken info of the transaction if the tx has destination tokenId</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getPendingRequests.html#_Token">_Token</a></td><td>N</td></tr><tr><td>fee</td><td>[Optional] <a href="get-pending-transactions.md#token">Token</a>, The fee of the transaction</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getPendingRequests.html#_Token">_Token</a></td><td>N</td></tr><tr><td>validUntil</td><td>[Optional] The validUntil of the transaction</td><td>1627904776</td><td>integer</td><td>N</td></tr><tr><td>toAccountId</td><td>[Optional] The toAccountId of the transaction if tx has a destination account</td><td>10006</td><td>integer</td><td>N</td></tr><tr><td>toAccountAddress</td><td>[Optional] The toAccountAddress of the transaction if tx has a destination account</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr><tr><td>storageId</td><td>[Optional] The storageId of the transaction</td><td>2</td><td>integer</td><td>N</td></tr><tr><td>orderA</td><td>[Optional] <a href="get-pending-transactions.md#order">Order</a>, The orderA of the transaction if tx is SpotTrade</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getPendingRequests.html#_Order">_Order</a></td><td>N</td></tr><tr><td>orderB</td><td>[Optional] <a href="get-pending-transactions.md#order">Order</a>, The orderB of the transaction if tx is SpotTrade</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getPendingRequests.html#_Order">_Order</a></td><td>N</td></tr><tr><td>valid</td><td>[Optional] The validness of the transaction</td><td>"false"</td><td>boolean</td><td>N</td></tr><tr><td>nonce</td><td>[Optional] The nonce of the transaction if it uses nonce</td><td>65</td><td>integer</td><td>N</td></tr><tr><td>minterAccountId</td><td>[Optional] The minterAccountId of the transaction if its a mint tx</td><td>10008</td><td>integer</td><td>N</td></tr><tr><td>minter</td><td>[Optional] The minter of the transaction if its a mint tx</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr><tr><td>nftToken</td><td>[Optional] The nftToken of the transaction if its a NFT related tx</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getPendingRequests.html#_Token">_Token</a></td><td>N</td></tr><tr><td>nftType</td><td>[Optional] The nftType of the transaction if its a mint tx</td><td>"EIP1155"</td><td>string</td><td>N</td></tr><tr><td>fromAddress</td><td>[Optional]  from address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr><tr><td>toAddress</td><td>[Optional] to address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr></tbody></table>

\
Model
-----

### Token

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>tokenId</td><td>[Optional] The tokenId of the token</td><td>"6"</td><td><a href="https://docs-uat.loopring.io/en/REST_APIS.html#ResultInfo">Result<br>Info</a></td><td>N</td></tr><tr><td>tokenAddress</td><td>[Optional]  The token Address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr><tr><td>nftData</td><td>[Optional] The nftData of the NFT token</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085"</td><td>string</td><td>N</td></tr><tr><td>nftId</td><td>[Optional] The NFT_ID of the NFT token</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085"</td><td>string</td><td>N</td></tr><tr><td>amount</td><td>[Optional] The token amount</td><td>"100"</td><td>string</td><td>N</td></tr></tbody></table>



### Order

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>storageID</td><td>The storageId of the order</td><td>6</td><td>integer</td><td>Y</td></tr><tr><td>accountID</td><td>The accountID of the order</td><td>10006</td><td>integer</td><td>Y</td></tr><tr><td>amountS</td><td>The amountS of the order</td><td>"100"</td><td>string</td><td>Y</td></tr><tr><td>amountB</td><td>The amountB of the order</td><td>"600"</td><td>string</td><td>Y</td></tr><tr><td>tokenS</td><td>The tokenS of the order</td><td>6</td><td>integer</td><td>Y</td></tr><tr><td>tokenB</td><td>The tokenB of the order</td><td>32768</td><td>integer</td><td>Y</td></tr><tr><td>validUntil</td><td>The validUntil of the order</td><td>1235123512</td><td>integer</td><td>Y</td></tr><tr><td>taker</td><td>The taker of the order</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>feeBips</td><td>The feeBips of the order</td><td>60</td><td>integer</td><td>Y</td></tr><tr><td>isAmm</td><td>If the order isAmm</td><td>"true"</td><td>boolean</td><td>Y</td></tr><tr><td>nftData</td><td>The nftData of the order, if its NFT order</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>fillS</td><td>The fillS of the order</td><td>500</td><td>integer</td><td>Y</td></tr></tbody></table>

## Sample code

### Request

```
GET api/v3/block/getPendingRequests
```

```
https://uat2.loopring.io/api/v3/block/getPendingRequests
```

### Response

```
[{
	"txType": "SpotTrade",
	"orderA": {
		"storageID": 16,
		"accountID": 88240,
		"amountS": "24555248000000000000000",
		"amountB": "12487500000",
		"tokenS": 1,
		"tokenB": 6,
		"validUntil": 1658444756,
		"taker": "",
		"feeBips": 10,
		"isAmm": false,
		"nftData": "",
		"fillS": 9158448
	},
	"orderB": {
		"storageID": 526024,
		"accountID": 108,
		"amountS": "12489000000",
		"amountB": "24555200000000000000000",
		"tokenS": 6,
		"tokenB": 1,
		"validUntil": 2147483647,
		"taker": "",
		"feeBips": 0,
		"isAmm": true,
		"nftData": "",
		"fillS": 2746330
	},
	"valid": true
}, {
	"txType": "Transfer",
	"accountId": 61279,
	"token": {
		"tokenId": 32980,
		"nftData": "0x002c471c82f1912eb3b3aff8c8b509c2126861bab0444533dbc17c06704f2235",
		"amount": "1"
	},
	"toToken": {
		"tokenId": 32899
	},
	"fee": {
		"tokenId": 1,
		"amount": "80900000000000000"
	},
	"validUntil": 1658444653,
	"toAccountId": 109068,
	"toAccountAddress": "0xd319373c55864b48e9edd03c08bade589443eff4",
	"storageId": 25
}]
```
