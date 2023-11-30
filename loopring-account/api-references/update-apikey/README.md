---
description: >-
  Change the ApiKey associated with the user's account. The current ApiKey must
  be provided as the value of the X-API-KEY HTTP header.
---

# Update apiKey

## EndPoint

```
POST /api/v3/apiKey
```

## Header

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>X-API-KEY</td><td>ApiKey</td><td>"HlkcGxbqBeaF76j4rvPaOasyfPwnkQ6B6DQ6THZWbvrAGxzEdulXQvOKLrRWZLnN"</td><td></td><td></td></tr><tr><td>X-API-SIG</td><td><a href="../../../resources/signature/eddsa-signature/">EDDSA Signature</a>, it's the <a href="../../../resources/request-signing/#special-api-request-signatures">request signing</a></td><td>"0xccf0a141fce2dc5cbbd4f802c52220e9e2ce260e86704d6258603eb346eefe2d4a450005c362b223b2842d087f7065ea5eee0314531adf6a580fce64c25dca81c"</td><td></td><td>Y</td></tr></tbody></table>

## Request

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>user account ID</td><td>10010</td><td>integer</td><td>Y</td></tr></tbody></table>

## Response

<table><thead><tr><th>Field</th><th>Description</th><th>Example</th><th data-hidden>Type</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>apiKey</td><td>ApiKey</td><td>"6BJaCehh0z4ta4TW5vwoKyo0yk5FdXkQxpt8AStG49aU3dMN C9jid6syyWPEMtTt"</td><td>string</td><td>Y</td></tr></tbody></table>
