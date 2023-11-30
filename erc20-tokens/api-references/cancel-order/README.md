---
description: Cancel order using order hash or client-side ID.
---

# Cancel Order

## EndPoint

```
DELETE api/v3/order
```



## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td></td><td>Y</td></tr><tr><td>X-API-SIG</td><td>EDDSA Signature, it's the <a href="../../../resources/request-signing/#special-api-request-signatures">request signing</a></td><td>"0xeb14773e8a07d19bc4fe56e36d041dcb0026bf21e05c7652f7e92160deaf5ea9c4fe56e34773e86d041dcbeb1a07d19b002652f7e92160deaf5e6bf21e05c7a9002652f7e92160deaf5e6bf21e05c7a9eb14773e8a07d19bc4fe56e36d041dcb"</td><td></td><td></td></tr></tbody></table>



## Request

<table><thead><tr><th width="150">Query Param</th><th>Description</th><th>Example</th><th data-hidden></th><th data-hidden></th><th data-hidden></th></tr></thead><tbody><tr><td>accountId</td><td>account ID</td><td></td><td></td><td></td><td></td></tr><tr><td>orderHash</td><td><mark style="color:orange;">(Optional)</mark> The order hash of submit order response</td><td>"0x05a97490e92ded027f65c4bebf3bad63813f4ce8c7255335894566b2eee90206"</td><td></td><td></td><td></td></tr><tr><td>clientOrderId</td><td><mark style="color:orange;">(Optional)</mark> The clieetOrderId of submit order</td><td>"202003180000 00001010"</td><td></td><td></td><td></td></tr></tbody></table>



## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>hash</td><td>The hash identifier set by the user at the time of submission, can use this hash to get the order info</td><td>"0x05a97490e92ded027f65c4bebf3bad63813f4ce8c7255335894566b2eee90206"</td><td>string</td><td>Y</td></tr><tr><td>clientOrderId</td><td>The clientOrderId of the submitted order</td><td></td><td></td><td></td></tr><tr><td>status</td><td>Order status of submit order response Allowable : ['processing', 'processed', 'cancelling', 'cancelled', 'expired', 'failed']</td><td>"processing"</td><td>string</td><td>Y</td></tr><tr><td>isIdempotent</td><td>Idempotent of submit transfer response, submit same transfer again idempotent will be true</td><td>"false"</td><td>boolean</td><td>Y</td></tr></tbody></table>
