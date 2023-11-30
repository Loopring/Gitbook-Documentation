---
description: Subscribe to this topic to receive notifications about user balance update.
---

# Account Notification

### Rules <a href="#rules" id="rules"></a>

* Topic name: `account`&#x20;
* ApiKey requred: Yes

### Parameters <a href="#parameters" id="parameters"></a>

This topic has an optional flag: `v3`, which indicates the response is for v3 which has also include NFT info. if the flag is false or absent, the response is just like before.

<table><thead><tr><th>Parameter</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>(Optional) not required as apiKey also link to an account</td><td>N</td></tr><tr><td>v3</td><td>(Optional) If it's a v3 sub which contains NFT info, default is false for compatible with previous sub topic</td><td>N</td></tr></tbody></table>

### Notification example <a href="#notification-example" id="notification-example"></a>

```json
{
    "topic": {
        "topic:": "account"
    },
    "ts":1584717910000,
    "data": {
        "accountId":1,
        "totalAmount": "24439253519655",
        "tokenId": 2,
        "amountLocked": "0"
    }
}
```



### Data Model <a href="#data-model" id="data-model"></a>

**Notification**

If v3 is `true`:

<table><thead><tr><th>Field</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>topic</td><td>JSON</td><td>Topic and parameters</td><td>Y</td></tr><tr><td>ts</td><td>integer</td><td>Notification timestamp (milliseconds)</td><td>Y</td></tr><tr><td>data</td><td><a href="account-notification.md#balancev3">BalanceV3</a></td><td>User's new balances (NFT info included)</td><td>Y</td></tr></tbody></table>

Otherwise:

<table><thead><tr><th>Field</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>topic</td><td>JSON</td><td>Topic and parameters</td><td>Y</td></tr><tr><td>ts</td><td>integer</td><td>Notification timestamp (milliseconds)</td><td>Y</td></tr><tr><td>data</td><td><a href="account-notification.md#balance">Balance</a></td><td>User's new balances</td><td>Y</td></tr></tbody></table>

#### **BalanceV3**

<table><thead><tr><th>Field</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>integer</td><td>Account ID</td><td>Y</td></tr><tr><td>tokenId</td><td>integer</td><td>Token ID</td><td>Y</td></tr><tr><td>total</td><td>string</td><td>Total token balance</td><td>Y</td></tr><tr><td>locked</td><td>string</td><td>Token balance locked by orders</td><td>Y</td></tr><tr><td>nftId</td><td>string</td><td>(Optional)NFT ID if it's NFT token</td><td>N</td></tr><tr><td>nftData</td><td>string</td><td>(Optional)NFT hash data if it's NFT token</td><td>N</td></tr><tr><td>tokenAddress</td><td>string</td><td>(Optional)NFT token address if it's NFT token</td><td>N</td></tr></tbody></table>

#### **Balance**

<table><thead><tr><th>Field</th><th>Type</th><th>Note</th><th data-hidden>Required</th></tr></thead><tbody><tr><td>accountId</td><td>integer</td><td>Account ID</td><td>Y</td></tr><tr><td>tokenId</td><td>integer</td><td>Token ID</td><td>Y</td></tr><tr><td>totalAmount</td><td>string</td><td>Total token balance</td><td>Y</td></tr><tr><td>amountLocked</td><td>string</td><td>Token balance locked by orders</td><td>Y</td></tr></tbody></table>
