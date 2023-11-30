# Get NFT Assets

## EndPoint

```
GET /api/v3/user/nft/balances
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey, can use a valid apiKey to get other address asset</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td>string</td><td>Y</td></tr></tbody></table>

\
Request
-------

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td><mark style="color:orange;">(Optional)</mark> AccountID, accountId or address is required</td><td>1</td><td>integer</td><td>Y</td></tr><tr><td>address</td><td><mark style="color:orange;">(Optional)</mark> Address, accountId or address is required</td><td>"0x8656920c85342d646E5286Cb841F90209272ABeb"</td><td></td><td></td></tr><tr><td>nftDatas</td><td><mark style="color:orange;">(Optional)</mark> The Loopring's NFT token data identifier which is a hash string of NFT token address and NFT_ID, separated by "," </td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085,0xc3a9053f313eef7c932351ca7100400f7c186fa16209c018f7f 1dba8aa831085"</td><td>string</td><td>N</td></tr><tr><td>tokenAddrs</td><td><mark style="color:orange;">(Optional)</mark> NFT token address, separated by "," </td><td>"0x8656920c85342d646E5286Cb841F90209272ABeb,0x8656920c85342d646E5286Cb841F90209272ABec"</td><td></td><td></td></tr><tr><td>tokenIds</td><td><mark style="color:orange;">(Optional)</mark> The token slot ID in loopring DEX, separated by "," </td><td>"32768,32769,32770"</td><td></td><td></td></tr><tr><td>offset</td><td><mark style="color:orange;">(Optional)</mark> Number of records to skip</td><td>10</td><td></td><td></td></tr><tr><td>limit</td><td><p><mark style="color:orange;">(Optional)</mark> Number of records to return.</p><p>Default is 20, max is 50</p></td><td>30</td><td></td><td></td></tr><tr><td>nonZero</td><td><mark style="color:orange;">(Optional)</mark> Hide 0 balance NFT token, default is true</td><td>true</td><td></td><td></td></tr><tr><td>metadata</td><td><mark style="color:orange;">(Optional)</mark> Return the metadata of the nft</td><td>false</td><td></td><td></td></tr></tbody></table>

## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>totalNum</td><td>total number</td><td>100</td><td>integer</td><td>Y</td></tr><tr><td>data</td><td>List[<a href="./#combinedbalance">Combined<br>Balance</a>]</td><td></td><td>string</td><td>Y</td></tr></tbody></table>

##

## Model

### **CombinedBalance**

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>AccountID</td><td>10110</td><td>integer</td><td>Y</td></tr><tr><td>tokenId</td><td>tokenId</td><td>32768</td><td>integer</td><td>Y</td></tr><tr><td>nftData</td><td>(Optional) Users NFT token nftData</td><td>"0xf7c932351186c3a9053f313eefa16209c018f7f1dba8aa8ca7100400f7c31085"</td><td>string</td><td>N</td></tr><tr><td>tokenAddress</td><td>(Optional) token address</td><td>"0x8656920c85342d646E5286Cb841F90209272ABeb"</td><td>string</td><td>N</td></tr><tr><td>nftType</td><td>nft type</td><td>ERC1155 or ERC721</td><td></td><td></td></tr><tr><td>nftId</td><td>(Optional) nft id</td><td>"100"</td><td>string</td><td>N</td></tr><tr><td>total</td><td>total amount</td><td>"1000"</td><td>string</td><td>Y</td></tr><tr><td>locked</td><td>frozen amount</td><td>"2"</td><td>string</td><td>Y</td></tr><tr><td>pending</td><td><a href="./#pendingbalance">pending balance</a></td><td>"{withdraw:0, deposit:0}"</td><td><a href="https://docs-uat.loopring.io/en/dex_apis/getUserNftBalances.html#PendingBalance">Pending<br>Balance</a></td><td>Y</td></tr><tr><td>isCounterFactualNFT</td><td>is counterFactual NFT or not</td><td>true</td><td></td><td></td></tr><tr><td>deploymentStatus</td><td>tokenAddress deploy status</td><td>status in NOT_DEPLOYED, DEPLOYING, DEPLOYED</td><td></td><td></td></tr></tbody></table>

### **PendingBalance**

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>withdraw</td><td>Withdrawal pending balance which means the token is in withdrawal state but not arrived L1</td><td>"100000000000<br>00"</td><td>string</td><td>Y</td></tr><tr><td>deposit</td><td>Deposit pending balance which means the token is in deposit state but not arrived L2</td><td>"100000000000<br>00"</td><td>string</td><td>Y</td></tr></tbody></table>

