# Storage Id

Fetches the next order id for a given sold token. If the need arises to repeatedly place orders in a short span of time, the order id can be initially fetched through the API and then managed locally. Each new order id can be derived from adding 2 to the last one.

## EndPoint

```
GET api/v3/storageId
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey, a valid apiKey is ok</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td>string</td><td>Y</td></tr></tbody></table>



## Request

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>Loopring account identifier</td><td>10110</td><td>integer</td><td>Y</td></tr><tr><td>sellTokenId</td><td>The unique identifier of the token which the user wants to sell in the next order.</td><td>0</td><td>integer</td><td>Y</td></tr><tr><td>maxNext</td><td>(Optional) Return the max of the next available storageId, so any storageId > returned value is available, to help users manage storageId by themselves. for example, if [20, 60, 100] is available, all other ids &#x3C; 100 are used before, the user gets 20 if the flag is false (and 60 in the next run), but gets 100 if the flag is true, so he can use 102, 104 freely</td><td>false</td><td>boolean</td><td>N</td></tr></tbody></table>



## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>orderId</td><td>Next storage ID for order request, must be even</td><td>100</td><td>integer</td><td>N</td></tr><tr><td>offchainId</td><td>Next storage ID for off-chain requests, i.e., transfer/withdraw/updateAccount, must be odd</td><td>101</td><td>integer</td><td>N</td></tr></tbody></table>
