# Get Trade History

## EndPoint

```
GET /api/v3/user/trades
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey, can use a valid apiKey to get other address asset</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td>string</td><td>Y</td></tr></tbody></table>

\
Request
-------

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>Account ID, some hash query APIs do not need it if in hash query mode, check required flag of each API to see if it is a must.</td><td>1</td><td>integer</td><td>Y</td></tr><tr><td>market</td><td><mark style="color:orange;">(Optional)</mark> Trading pair</td><td>"LRC-ETH"</td><td>string</td><td>N</td></tr><tr><td>orderHash</td><td><mark style="color:orange;">(Optional)</mark> Order hash</td><td>"0x9d114267e8<br>b261457d5670<br>93c13cf3deea<br>5f14c9235be2<br>6c6fa833dba1<br>2a9632"</td><td>string</td><td>N</td></tr><tr><td>offset</td><td><mark style="color:orange;">(Optional)</mark> Number of records to skip</td><td>1</td><td>integer</td><td>N</td></tr><tr><td>limit</td><td><mark style="color:orange;">(Optional)</mark> Number of records to return, max is 50</td><td>20</td><td>integer</td><td>N</td></tr><tr><td>fillTypes</td><td><mark style="color:orange;">(Optional)</mark> fillTypes<br>Allowable : ['dex', 'amm'],<br>dex means orderbook</td><td>"dex"</td><td>string</td><td>N</td></tr></tbody></table>



## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>totalNum</td><td>Total number of tradings</td><td>100</td><td>integer</td><td>Y</td></tr><tr><td>trades</td><td>List[List[string]]</td><td></td><td>List[List[string]]</td><td>Y</td></tr></tbody></table>

the 'trades' values are:

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>createdAt</td><td>timestamp</td><td>"1657638459610"</td><td>integer</td><td>Y</td></tr><tr><td>id</td><td>id</td><td>"8919527"</td><td>string</td><td>N</td></tr><tr><td>side</td><td>buy or sell</td><td>"SELL"</td><td>string</td><td>N</td></tr><tr><td>size</td><td>trade size</td><td>"453794000000000000000"</td><td>integer</td><td>N</td></tr><tr><td>price</td><td>price</td><td>"3.5669E-4"</td><td>integer</td><td>N</td></tr><tr><td>market</td><td>market</td><td>"LRC-ETH"</td><td>string</td><td>N</td></tr><tr><td>feeAmount</td><td>fee amount</td><td>"1618680000000000"</td><td></td><td></td></tr><tr><td>blockId</td><td>the trade in layer2 block, useless now</td><td>"24697"</td><td></td><td></td></tr><tr><td>indexInBlock</td><td>the index in block, useless now</td><td>"343"</td><td></td><td></td></tr><tr><td>accountId</td><td>user accountId</td><td>"147661"</td><td></td><td></td></tr><tr><td>tokenId</td><td>trade tokenId</td><td>"0"</td><td></td><td></td></tr><tr><td>storageId</td><td>user storageId</td><td>"2"</td><td></td><td></td></tr><tr><td>orderHash</td><td>the order hash</td><td>"0x0a417a8969caa753e335c08e079d5ac3bbe5a9453f3589868c6e3167a2181b58"</td><td></td><td></td></tr></tbody></table>
