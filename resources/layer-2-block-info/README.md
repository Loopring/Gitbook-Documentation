# Layer 2 block info

## EndPoint

```
GET api/v3/block/getBlock
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td>string</td><td>Y</td></tr></tbody></table>



## Request

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>id</td><td>block id number</td><td>200</td><td>string</td><td>N</td></tr></tbody></table>



## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>blockId</td><td>The num index of the block</td><td>1235</td><td>integer</td><td>Y</td></tr><tr><td>blockSize</td><td>The block size</td><td>64</td><td>integer</td><td>Y</td></tr><tr><td>exchange</td><td>The exchange address</td><td>"0xbbbbca6a90<br>1c926f240b89<br>eacb641d8aec<br>7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>txHash</td><td>The txHash of the block</td><td>"0xf7c9323511<br>86c3a9053f31<br>3eefa16209c0<br>18f7f1dba8aa<br>8ca7100400f7<br>c31085"</td><td>string</td><td>Y</td></tr><tr><td>status</td><td>The status of the block, WAIT_SUBMIT or SUBMITTED or COMPLETED</td><td>"COMPLETED"</td><td>string</td><td>Y</td></tr><tr><td>createdAt</td><td>The creation time of the block</td><td>1627904776000</td><td>integer</td><td>Y</td></tr><tr><td>transactions</td><td>List[<a href="./#blocktransaction">BlockTransaction</a>], The txs list inside the block</td><td>/</td><td>List[<a href="https://docs-uat.loopring.io/en/dex_apis/getBlock.html#TransactionBlock">Transaction<br>Block</a>]</td><td>Y</td></tr></tbody></table>

\
Model
-----

### BlockTransaction

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>txType</td><td>The txType of the transaction, one in [Noop,Deposit,Withdraw,Transfer,SpotTrade,AccountUpdate,AmmUpdate,JoinAmm,ExitAmm,SignatureVerification,NftMint,NftData]<br>Allowable : ['Noop', 'Deposit', 'Withdraw', 'Transfer', 'SpotTrade', 'AccountUpdate', 'AmmUpdate', 'JoinAmm', 'ExitAmm', 'SignatureVerification', 'NftMint', 'NftData']</td><td><p>"Deposit"</p><p>"Withdraw" </p><p>"Transfer" </p><p>"SpotTrade" "AccountUpdate" "AmmUpdate" </p><p>"JoinAmm" </p><p>"ExitAmm" "SignatureVerification" "NftMint"<br>"NftData"</p></td><td>string</td><td>Y</td></tr><tr><td>accountId</td><td>[Optional] The accountId of the transaction</td><td>10006</td><td>integer</td><td>N</td></tr><tr><td>owner</td><td>[Optional] The owner of the transaction</td><td>"0xbbbbca6a90<br>1c926f240b89<br>eacb641d8aec<br>7aeafd"</td><td>string</td><td>N</td></tr><tr><td>token</td><td>[Optional] <a href="./#token">Token</a>, The token info of the transaction</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getBlock.html#_Token">_Token</a></td><td>N</td></tr><tr><td>toToken</td><td>[Optional] <a href="./#token">Token</a>, The toToken info of the transaction if the tx has destination tokenId</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getBlock.html#_Token">_Token</a></td><td>N</td></tr><tr><td>fee</td><td>[Optional] <a href="./#token">Token</a>, The fee of the transaction</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getBlock.html#_Token">_Token</a></td><td>N</td></tr><tr><td>validUntil</td><td>[Optional] The validUntil of the transaction</td><td>1627904776</td><td>integer</td><td>N</td></tr><tr><td>toAccountId</td><td>[Optional] The toAccountId of the transaction if tx has a destination account</td><td>10006</td><td>integer</td><td>N</td></tr><tr><td>toAccountAddress</td><td>[Optional] The toAccountAddress of the transaction if tx has a destination account</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr><tr><td>storageId</td><td>[Optional] The storageId of the transaction</td><td>2</td><td>integer</td><td>N</td></tr><tr><td>orderA</td><td>[Optional] <a href="./#order">Order</a>, The orderA of the transaction if tx is SpotTrade</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getBlock.html#_Order">_Order</a></td><td>N</td></tr><tr><td>orderB</td><td>[Optional] <a href="./#order">Order</a>, The orderB of the transaction if tx is SpotTrade</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getBlock.html#_Order">_Order</a></td><td>N</td></tr><tr><td>valid</td><td>[Optional] The validness of the transaction</td><td>"false"</td><td>boolean</td><td>N</td></tr><tr><td>nonce</td><td>[Optional] The nonce of the transaction if it uses nonce</td><td>65</td><td>integer</td><td>N</td></tr><tr><td>minterAccountId</td><td>[Optional] The minterAccountId of the transaction if its a mint tx</td><td>10008</td><td>integer</td><td>N</td></tr><tr><td>minter</td><td>[Optional] The minter of the transaction if its a mint tx</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr><tr><td>nftToken</td><td>[Optional] The nftToken of the transaction if its a NFT related tx</td><td>/</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getBlock.html#_Token">_Token</a></td><td>N</td></tr><tr><td>nftType</td><td>[Optional] The nftType of the transaction if its a mint tx</td><td>"ERC1155"</td><td>string</td><td>N</td></tr><tr><td>fromAddress</td><td>[Optional] from address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr><tr><td>toAddress</td><td>[Optional] to address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr></tbody></table>



### Token

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>tokenId</td><td>[Optional] The tokenId of the token</td><td>"6"</td><td><a href="https://docs-uat.loopring.io/en/REST_APIS.html#ResultInfo">Result<br>Info</a></td><td>N</td></tr><tr><td>tokenAddress</td><td>[Optional]  The token Address</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>N</td></tr><tr><td>nftData</td><td>[Optional] The nftData of the NFT token</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085"</td><td>string</td><td>N</td></tr><tr><td>nftId</td><td>[Optional] The NFT_ID of the NFT token</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085"</td><td>string</td><td>N</td></tr><tr><td>amount</td><td>[Optional] The token amount</td><td>"100"</td><td>string</td><td>N</td></tr></tbody></table>



### Order

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>storageID</td><td>The storageId of the order</td><td>6</td><td>integer</td><td>Y</td></tr><tr><td>accountID</td><td>The accountID of the order</td><td>10006</td><td>integer</td><td>Y</td></tr><tr><td>amountS</td><td>The amountS of the order</td><td>"100"</td><td>string</td><td>Y</td></tr><tr><td>amountB</td><td>The amountB of the order</td><td>"600"</td><td>string</td><td>Y</td></tr><tr><td>tokenS</td><td>The tokenS of the order</td><td>6</td><td>integer</td><td>Y</td></tr><tr><td>tokenB</td><td>The tokenB of the order</td><td>32768</td><td>integer</td><td>Y</td></tr><tr><td>validUntil</td><td>The validUntil of the order</td><td>1235123512</td><td>integer</td><td>Y</td></tr><tr><td>taker</td><td>The taker of the order</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>feeBips</td><td>The feeBips of the order</td><td>60</td><td>integer</td><td>Y</td></tr><tr><td>isAmm</td><td>If the order isAmm</td><td>"true"</td><td>boolean</td><td>Y</td></tr><tr><td>nftData</td><td>The nftData of the order, if its NFT order</td><td>"0xbbbbca6a901c926f240b89eacb641d8aec7aeafd"</td><td>string</td><td>Y</td></tr><tr><td>fillS</td><td>The fillS of the order</td><td>500</td><td>integer</td><td>Y</td></tr></tbody></table>

## Sample code

### Request

```
GET api/v3/block/getBlock
```

```
https://uat2.loopring.io/api/v3/block/getBlock?id=200
```

### Response

```
{
	"blockId": 200,
	"blockSize": 16,
	"exchange": "0x2e76ebd1c7c0c8e7c2b875b6d505a260c525d25e",
	"txHash": "0xed78550231d3df1e68de286980628774c2bcfb1a72a09a20feaf48e8d9acdb0b",
	"status": "COMPLETED",
	"createdAt": 1610164628895,
	"transactions": [{
		"txType": "Deposit",
		"accountId": 10010,
		"owner": "0x6b1029c9ae8aa5eea9e045e8ba3c93d380d5bdda",
		"token": {
			"tokenId": 2,
			"amount": "1000000"
		}
	}]
}
```
