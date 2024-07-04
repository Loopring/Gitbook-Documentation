---
description: Get deposit/transfer/withdraw history
---

# Get NFT Transactions

## EndPoint

```
GET /api/v3/user/nft/transactions
```

## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOayfPwnkQ6B6DQ6THZWbvrGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr></tbody></table>

## Request

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>users accountId.</td><td>10001</td><td>integer</td><td>Y</td></tr><tr><td>offset</td><td><mark style="color:orange;">(Optional)</mark> Offset number</td><td>2</td><td>integer</td><td>N</td></tr><tr><td>limit</td><td><mark style="color:orange;">(Optional)</mark> Number of records to return, default is 50</td><td>20</td><td>integer</td><td>N</td></tr><tr><td>types</td><td><mark style="color:orange;">(Optional)</mark> default is "mint,deposit,transfer,deploy,onchain_withdrawal,offchain_withdrawal", you  can use one or more of them</td><td>"mint","transfer","deposit"...</td><td></td><td></td></tr><tr><td>hashes</td><td><mark style="color:orange;">(Optional)</mark> hash, separate by ","</td><td></td><td></td><td></td></tr><tr><td>nftData</td><td><mark style="color:orange;">(Optional)</mark> nft datas, separate by ","</td><td></td><td></td><td></td></tr></tbody></table>

## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>totalNum</td><td>total transaction number</td><td>100</td><td>integer</td><td>Y</td></tr><tr><td>transactions</td><td>List[<a href="./#nfttxdata">NftTxData</a>]</td><td>/</td><td>List[<a href="https://docs.loopring.io/en/dex_apis/getNftTransfers.html#NftTransferData">Nft<br>Transfer<br>Data</a>]</td><td>Y</td></tr></tbody></table>

##

## Model

### NftTxData

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>id</td><td>the transaction id</td><td>1</td><td>string</td><td>Y</td></tr><tr><td>requestId</td><td></td><td></td><td>integer</td><td>Y</td></tr><tr><td>hash</td><td>layer2 hash</td><td></td><td>string</td><td>Y</td></tr><tr><td>txHash</td><td>layer1 hash, the value used when it's withdraw</td><td></td><td>string</td><td>Y</td></tr><tr><td>accountId</td><td>account Id</td><td>/</td><td>integer</td><td>Y</td></tr><tr><td>owner</td><td>owner address</td><td>/</td><td>string</td><td>Y</td></tr><tr><td>status</td><td>status in "pending,processing,processed,received,failed"</td><td>"processed"</td><td>string</td><td>Y</td></tr><tr><td>nftData</td><td>layer2 nft data</td><td>/</td><td>string</td><td>Y</td></tr><tr><td>amount</td><td>amount</td><td>"2"</td><td>string</td><td>Y</td></tr><tr><td>feeTokenSymbol</td><td>fee token symbol</td><td>"LRC"</td><td>string</td><td>Y</td></tr><tr><td>feeAmount</td><td>fee amount</td><td>"10000000000000"</td><td>string</td><td>Y</td></tr><tr><td>createdAt</td><td>create timestamp</td><td></td><td>integer</td><td>Y</td></tr><tr><td>updatedAt</td><td>update timestamp</td><td></td><td>integer</td><td>Y</td></tr><tr><td>memo</td><td>memo, used when it's transfer</td><td>/</td><td>string</td><td>Y</td></tr><tr><td>receiverAddress</td><td>receiver address</td><td>/</td><td>integer</td><td>Y</td></tr><tr><td>receiver</td><td>receiver account Id</td><td></td><td></td><td></td></tr><tr><td>senderAddress</td><td>sender address</td><td>/</td><td>string</td><td>Y</td></tr><tr><td>withdrawalInfo</td><td>WithdrawalInfo, withdraw info</td><td>/</td><td><a href="https://docs.loopring.io/en/dex_apis/getNftTransfers.html#BlockIdInfo">BlockId<br>Info</a></td><td>N</td></tr><tr><td>minterInfo</td><td>MinterInfo, minter info</td><td></td><td></td><td></td></tr><tr><td>storageInfo</td><td></td><td>/</td><td><a href="https://docs.loopring.io/en/dex_apis/getNftTransfers.html#StorageInfo">Storage<br>Info</a></td><td>N</td></tr></tbody></table>

### **MinterInfo**

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>minter account Id</td><td>10110</td><td>integer</td><td>Y</td></tr><tr><td>minter</td><td>minter address, if NFT withdraw to layer1 then deposit to layer2, the miner address is tokenAddress</td><td></td><td>integer</td><td>Y</td></tr><tr><td>originalMinter</td><td>original minter address, if NFT withdraw to layer1 then deposit to layer2, we'll search the original minter and fill to this value</td><td></td><td>integer</td><td>Y</td></tr></tbody></table>



### **WithdrawalInfo**

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>recipient</td><td>recipient address</td><td></td><td>integer</td><td>Y</td></tr><tr><td>fastStatus</td><td></td><td></td><td>integer</td><td>Y</td></tr><tr><td>distributeHash</td><td>layer1 hash</td><td></td><td>integer</td><td>Y</td></tr></tbody></table>



### **StorageInfo**

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>account Id</td><td>10110</td><td>integer</td><td>Y</td></tr><tr><td>tokenId</td><td>token Id</td><td>32768</td><td>integer</td><td>Y</td></tr><tr><td>storageId</td><td>storage Id</td><td>1</td><td>integer</td><td>Y</td></tr></tbody></table>
